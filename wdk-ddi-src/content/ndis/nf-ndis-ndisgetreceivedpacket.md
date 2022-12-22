---
UID: NF:ndis.NdisGetReceivedPacket
tech.root: 
title: NdisGetReceivedPacket
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: <= DISPATCH_LEVEL
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
 - NdisGetReceivedPacket
f1_keywords:
 - NdisGetReceivedPacket
 - ndis/NdisGetReceivedPacket
dev_langs:
 - c++
helpviewer_keywords:
 - NdisGetReceivedPacket
---

# NdisGetReceivedPacket function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisGetReceivedPacket** retrieves a packet that was received from the underlying driver.

## -parameters

### -param NdisBindingHandle [in]

Specifies the handle that was returned by [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md) that identifies the target NIC or the virtual adapter of the underlying driver to which the calling driver is bound.

### -param MacContext [in]

Specifies a context handle that the underlying driver associates with the packet received from the network. This handle was passed as an input parameter to the calling driver's [**ProtocolReceive**](https://msdn.microsoft.com/library/ff563246\(v=vs.85\)) function. This handle is opaque to the calling driver and reserved for use by the underlying driver that made the indication.

## -returns

Returns a pointer to a packet descriptor that contains data that was received on the underlying driver.

## -remarks

Several protocol or intermediate drivers can be bound to a single underlying NIC, and each such driver can receive an indication for the same packet. Such a packet is read-only to these drivers. Each such driver's *ProtocolReceive* function determines whether to call **NdisGetReceivedPacket** to retrieve the indicated packet.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**NdisOpenAdapter**](nf-ndis-ndisopenadapter.md)
