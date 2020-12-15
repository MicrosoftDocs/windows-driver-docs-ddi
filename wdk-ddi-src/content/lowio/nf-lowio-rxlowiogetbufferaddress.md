---
UID: NF:lowio.RxLowIoGetBufferAddress
title: RxLowIoGetBufferAddress function (lowio.h)
description: RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.
old-location: ifsk\rxlowiogetbufferaddress.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxLowIoGetBufferAddress function"]
ms.keywords: RxLowIoGetBufferAddress, RxLowIoGetBufferAddress function [Installable File System Drivers], ifsk.rxlowiogetbufferaddress, lowio/RxLowIoGetBufferAddress, rxref_b45afb50-cf03-4450-9e96-3d8f08392eb6.xml
req.header: lowio.h
req.include-header: Rxcontx.h, Lowio.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxLowIoGetBufferAddress
 - lowio/RxLowIoGetBufferAddress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - lowio.h
api_name:
 - RxLowIoGetBufferAddress
---

# RxLowIoGetBufferAddress function


## -description

**RxLowIoGetBufferAddress** returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.

## -parameters

### -param RxContext 

[in]
A pointer to the RX_CONTEXT structure for this request.

## -returns

**RxLowIoGetBufferAddress **returns a mapped address pointer on success or a **NULL** on failure.

## -remarks

**RxLowIoGetBufferAddress** checks that the **ParamsFor.ReadWrite.ByteCount** member of the **LowIoContext** member of the *RxContext* variable is greater than zero and returns a **NULL** pointer if this is not the case.

**RxLowIoGetBufferAddress** calls **MmGetSystemAddressForMdlSafe** to retrieve the mapped address.

## -see-also

[MmGetSystemAddressForMdlSafe](/windows-hardware/drivers/kernel/mm-bad-pointer)

[RX_CONTEXT](../rxcontx/ns-rxcontx-_rx_context.md)

[RxLowIoCompletion](./nf-lowio-rxlowiocompletion.md)

[RxMapSystemBuffer](../rxprocs/nf-rxprocs-rxmapsystembuffer.md)

[RxNewMapUserBuffer](/windows-hardware/drivers/ifs/rxnewmapuserbuffer)
