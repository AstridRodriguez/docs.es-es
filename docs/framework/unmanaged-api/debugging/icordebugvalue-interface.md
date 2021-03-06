---
title: ICorDebugValue (Interfaz1)
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41afc2e4305034340ad408e52ce08372bf8962dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507452"
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue (Interfaz1)
Representa un valor en el proceso que se está depurando. El valor puede ser de lectura o un valor de escritura.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Este método no está implementado actualmente.|  
|[GetAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Obtiene la dirección de esta `ICorDebugValue` objeto, que se está depurando.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.|  
|[GetType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Obtiene el tipo primitivo de este `ICorDebugValue` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 En general, la propiedad de un objeto de valor se pasa cuando se devuelve. El destinatario es responsable de quitar una referencia del objeto cuando haya finalizado con el objeto.  
  
 Dependiendo de dónde se recupera el valor de, el valor es posible que no siguen siendo válido después de que se reanuda el proceso. Por lo tanto, en general, el valor no debe mantenerse durante una llamada de la [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también




- [ICorDebugValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
