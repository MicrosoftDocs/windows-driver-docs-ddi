---
UID: NF:ndis.NdisCloseAdapter
tech.root: netvista
title: NdisCloseAdapter
ms.date: 01/04/2023
targetos: Windows
description: NdisCloseAdapter releases the binding established and the resources allocated when the protocol called NdisOpenAdapter.
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
 - NdisCloseAdapter
f1_keywords:
 - NdisCloseAdapter
 - ndis/NdisCloseAdapter
dev_langs:
 - c++
helpviewer_keywords:
 - NdisCloseAdapter
---

# NdisCloseAdapter function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](../_netvista/index.md). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisCloseAdapter** releases the binding established and the resources allocated when the protocol called [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md).

## -parameters

### -param Status [out]  

Pointer to a caller-supplied variable in which this function returns the status of the close operation, which can be one of the following values:

- NDIS\_STATUS\_SUCCESS  
  The binding was closed and all resources pertaining to that binding have been released.

- NDIS\_STATUS\_PENDING  
  A close-adapter request is being handled asynchronously, and the caller's [**ProtocolCloseAdapterComplete**](https://msdn.microsoft.com/library/ff562502\(v=vs.85\)) function will be called when the close operation is done.

### -param NdisBindingHandle [in]

Specifies the handle returned by **NdisOpenAdapter** that identifies the virtual adapter or NIC to be closed.

## -remarks

Return value: None

A protocol driver typically calls **NdisCloseAdapter** from its [**ProtocolUnbindAdapter**](https://msdn.microsoft.com/library/ff563260\(v=vs.85\)) function. It can also call **NdisCloseAdapter** from its [**ProtocolBindAdapter**](https://msdn.microsoft.com/library/ff562465\(v=vs.85\)) function, for example, if it failed to set an OID value after calling [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md) to set up a binding.

As soon as a protocol calls **NdisCloseAdapter**, the handle at *NdisBindingHandle* should be considered invalid by the caller. It is a programming error to pass this handle in any subsequent call to an *NdisXxx* function.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use NdisCloseAdapterEx instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**NdisCompleteUnbindAdapter**](https://msdn.microsoft.com/library/ff551048\(v=vs.85\))
- [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md)
- [**ProtocolCloseAdapterComplete**](https://msdn.microsoft.com/library/ff562502\(v=vs.85\))
- [**ProtocolUnbindAdapter**](https://msdn.microsoft.com/library/ff563260\(v=vs.85\))
