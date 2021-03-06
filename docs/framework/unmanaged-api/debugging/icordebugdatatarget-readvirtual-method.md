---
title: ICorDebugDataTarget::ReadVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 20cea94961a250c3981d892910da1dcee20a060b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783742"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>ICorDebugDataTarget::ReadVirtual-Methode
Ruft einen Block von zusammenhängenden Arbeitsspeicher ab, der bei der angegebenen Adresse beginnt, und gibt ihn im angegebenen Puffer zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Parameters  
 `address`  
 in Die Startadresse des angeforderten Speichers.  
  
 `pbuffer`  
 vorgenommen Der Puffer, in dem der Arbeitsspeicher gespeichert wird.  
  
 `bytesRequested`  
 in Die Anzahl der Bytes, die von der Zieladresse abgeleitet werden sollen.  
  
 `pBytesRead`  
 vorgenommen Die Anzahl der tatsächlich von der Zieladresse gelesenen Bytes. Dies kann weniger als `bytesRequested`sein.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das erste Byte (an der angegebenen Startadresse) gelesen werden kann, sollte der-Befehl einen Erfolg zurückgeben (um das effiziente Lesen von Datenstrukturen mit selbst beschreibender Länge zu unterstützen, wie z. b. auf NULL endende Zeichen folgen).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
