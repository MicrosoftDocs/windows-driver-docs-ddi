---
UID: NF:ndis.NdisMRegisterUnloadHandler
tech.root: netvista
title: NdisMRegisterUnloadHandler
ms.date: 01/04/2023
targetos: Windows
description: The NdisMRegisterUnloadHandler function registers an unload handler for a driver.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisMRegisterUnloadHandler
f1_keywords:
 - NdisMRegisterUnloadHandler
 - ndis/NdisMRegisterUnloadHandler
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMRegisterUnloadHandler
---

# NdisMRegisterUnloadHandler function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

The **NdisMRegisterUnloadHandler** function registers an unload handler for a driver.

## -parameters

### -param NdisWrapperHandle [in]

Specifies the handle returned by [**NdisMInitializeWrapper**](https://msdn.microsoft.com/library/ff553547\(v=vs.85\)).

### -param UnloadHandler [in]

Specifies the entry point for the driver's unload routine. An unload routine is declared as follows:

```cpp
VOID
(*PDRIVER_UNLOAD) (
    IN struct _DRIVER_OBJECT *DriverObject
    );
```

## -remarks

A driver calls **NdisMRegisterUnloadHandler** from its **DriverEntry** function after **DriverEntry** has called [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\)) or [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md). **NdisMRegisterUnloadHandler** registers an unload handler for the driver.

The functionality of the unload handler is driver-specific. For example, an intermediate driver should register an unload handler that calls [**NdisDeregisterProtocol**](nf-ndis-ndisderegisterprotocol.md) to deregister the protocol portion of the intermediate driver. The unload handler should also perform any necessary cleanup operations, such as deallocating resources used by the protocol portion of the driver.

A miniport driver, such as a load-balancing miniport driver, that monitors more than one miniport driver instance should register an unload handler that cleans up state information and deallocates resources after the miniport driver instances that it monitors are halted. Note that an unload handler differs from a [**MiniportHalt**](https://msdn.microsoft.com/library/ff549451\(v=vs.85\)) function: the unload handler has a more global scope, whereas the scope of the MiniportHalt function is restricted to a particular miniport driver instance.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563654"><strong>NdisMRegisterMiniportDriver</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**DriverEntry of NDIS Miniport Drivers**](https://msdn.microsoft.com/library/Ff548818)
- [**MiniportHalt**](https://msdn.microsoft.com/library/ff549451\(v=vs.85\))
- [**NdisDeregisterProtocol**](nf-ndis-ndisderegisterprotocol.md)
- [**NdisIMRegisterLayeredMiniport**](nf-ndis-ndisimregisterlayeredminiport.md)
- [**NdisMRegisterMiniport**](https://msdn.microsoft.com/library/ff553602\(v=vs.85\))
