---
title: ICorDebugUnmanagedCallback::DebugEvent-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
ms.openlocfilehash: cb52150a17c9ec8f4bbc25c13b85bce56b221eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791190"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent-Methode
Benachrichtigt den Debugger, dass ein natives Ereignis ausgelöst wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pDebugEvent`  
 in Ein Zeiger auf das Native Ereignis.  
  
 `fOutOfBand`  
 [in] `true`, wenn die Interaktion mit dem verwalteten Prozessstatus nach einem nicht verwalteten Ereignis nicht mehr möglich ist, bis der Debugger [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)aufruft. Andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn es sich bei dem gedebuggten Thread um einen Win32-Thread handelt, dürfen Sie keine Member der Win32-Debugschnittstelle verwenden. Sie können `ICorDebugController::Continue` nur in einem Win32-Thread und nur bei der Fortsetzung eines Out-of-Band-Ereignisses abrufen.  
  
 Der `DebugEvent`-Rückruf befolgt nicht die Standardregeln für Rückrufe. Wenn Sie `DebugEvent`aufgerufen wird, befindet sich der Prozess im unformatierten Zustand "OS-Debug beendet". Der Prozess wird nicht synchronisiert. Wenn dies erforderlich ist, wird automatisch der synchronisierte Status eingegeben, um Anforderungen nach Informationen über verwalteten Code zu erfüllen. Dies kann zu anderen Sch`DebugEvent` Rückrufen führen.  
  
 Aufrufen von [ICorDebugProcess:: cleareption TException](icordebugprocess-clearcurrentexception-method.md) für den Prozess, um ein Ausnahme Ereignis zu ignorieren, bevor der Prozess fortgesetzt wird. Wenn Sie diese Methode aufrufen, werden DBG_CONTINUE statt DBG_EXCEPTION_NOT_HANDLED bei der Continue-Anforderung gesendet. out-of-Band-Haltepunkte und einstufige Ausnahmen werden automatisch gelöscht. Out-of-Band-Ereignisse können jederzeit auftreten, auch wenn die zu debuggenden Anwendung beendet wird und ein ausstehendes in-Band-Ereignis bereits vorhanden ist.  
  
 In der .NET Framework Version 2,0 sollte der Debugger unmittelbar hinter einem Out-of-Band-breakpointereignis fortfahren. Der Debugger sollte die Methoden [ICorDebugProcess2:: abtmanagedbreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) und [ICorDebugProcess2:: ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) verwenden, um Breakpoints hinzuzufügen und zu entfernen. Diese Methoden überspringen alle out-of-Band-Haltepunkte automatisch. Daher sollten die einzigen out-of-Band-Haltepunkte, die verteilt werden, unformatierte Haltepunkte sein, die sich bereits im Anweisungs Datenstrom befinden, z. b. ein aufzurufende Win32-`DebugBreak` Funktion. Versuchen Sie nicht, `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)oder einen anderen Member der Debug- [API](index.md)zu verwenden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugUnmanagedCallback-Schnittstelle](icordebugunmanagedcallback-interface.md)
