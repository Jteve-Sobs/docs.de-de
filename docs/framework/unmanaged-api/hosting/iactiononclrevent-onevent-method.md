---
title: IActionOnCLREvent::OnEvent-Methode
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: 98807717fc913052dae15f9f3cbd462d4f537ad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126921"
---
# <a name="iactiononclreventonevent-method"></a>IActionOnCLREvent::OnEvent-Methode
Führt Rückrufe für Ereignisse aus, die mit einem Aufruf der [ICLROnEventManager:: registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) -Methode registriert wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `event`  
 in Einer der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) -Werte, der den Ereignistyp angibt.  
  
 `data`  
 in Ein Zeiger auf ein Objekt, das Details über `event`enthält.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`OnEvent` erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE|Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.|  
|HOST_E_TIMEOUT|Timeout des Aufrufes.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.|  
|E_FAIL|Ein unbekannter schwerwiegender Fehler ist aufgetreten. Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden. Nachfolgende Aufrufe einer beliebigen Hostingmethode geben HOST_E_CLRNOTAVAILABLE zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Der `data`-Parameter ist ein Zeiger auf ein Objekt des nicht angegebenen Typs. Wenn der `event`-Parameter `Event_DomainUnload`ist, ist `data` der numerische Bezeichner für die entladene <xref:System.AppDomain>. Der Host kann mithilfe dieses Bezeichners als Schlüssel geeignete Aktion ausführen.  
  
 Wenn `event` `Event_MDAFired`ist, ist `data` ein Zeiger auf eine [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz, die die Nachrichten Ausgabe eines Assistenten für verwaltetes Debuggen (MDA) enthält. MDAs sind eine Funktion der CLR, die Entwickler beim Debuggen unterstützt, indem XML-Meldungen zu Ereignissen erzeugt werden, die andernfalls schwierig zu Trap laufen sind. Solche Nachrichten können besonders beim Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code nützlich sein. Weitere Informationen finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [EClrEvent-Enumeration](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLROnEventManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [MDAInfo-Struktur](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
