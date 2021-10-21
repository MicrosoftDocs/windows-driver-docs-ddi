---
UID: NF:spbcx.SpbRequestGetTransferParameters
title: SpbRequestGetTransferParameters function (spbcx.h)
description: The SpbRequestGetTransferParameters method retrieves the transfer parameters for an individual transfer in an I/O transfer sequence.
old-location: spb\spbrequestgettransferparameters.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SpbRequestGetTransferParameters function"]
ms.keywords: SPB.spbrequestgettransferparameters, SpbRequestGetTransferParameters, SpbRequestGetTransferParameters method [Buses], spbcx/SpbRequestGetTransferParameters
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SpbRequestGetTransferParameters
 - spbcx/SpbRequestGetTransferParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - spbcxstubs.lib
 - spbcxstubs.dll
api_name:
 - SpbRequestGetTransferParameters
---

# SpbRequestGetTransferParameters function

## -description

The *SpbRequestGetTransferParameters* method retrieves the transfer parameters for an individual transfer in an [I/O transfer sequence](/windows-hardware/drivers/spb/i-o-transfer-sequences).

## -parameters

### -param SpbRequest

[in]
An [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles) handle to the I/O request from which to retrieve the transfer parameters. This parameter must be a handle to an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request.

### -param Index

[in]
The index of a transfer in the I/O transfer sequence. For more information, see the following Remarks section.

### -param TransferDescriptor

[out, optional]
A pointer to a caller-allocated [SPB_TRANSFER_DESCRIPTOR](./ns-spbcx-spb_transfer_descriptor.md) structure into which the method writes the transfer parameters. The *TransferDescriptor* parameter is optional and can be specified as NULL if the caller does not require the transfer parameters. For more information, see the [Remarks](#remarks) section.

### -param TransferBuffer

[out, optional]
A pointer to a location into which the method writes a pointer to an MDL (or an MDL chain) that describes the physical memory in the transfer buffer. The caller must not modify the contents of this MDL. This parameter is optional and can be set to NULL if the MDL is not needed. For more information, see the following Remarks section.

## -remarks

To request an I/O transfer sequence, a client (peripheral driver) of the SPB controller driver sends an [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence) request that contains a list of the transfers in the sequence. Your controller driver can call *SpbRequestGetTransferParameters* to obtain information about a particular transfer in the sequence.

The *Index* parameter is an index that identifies a particular transfer in the sequence. If N is the number of transfers in the sequence, valid indexes range from 0 to N–1. To determine the number of transfers in the sequence, call the [SpbRequestGetParameters](./nf-spbcx-spbrequestgetparameters.md) method. This method retrieves an [SPB_TRANSFER_DESCRIPTOR](./ns-spbcx-spb_transfer_descriptor.md) structure that contains the request parameters. The *TransferCount* member of this structure specifies the number of transfers in the sequence.

If *TransferDescriptor* is non-NULL, the caller must call the [SPB_TRANSFER_DESCRIPTOR_INIT](./nf-spbcx-spb_transfer_descriptor_init.md) function to initialize the structure before calling *SpbRequestGetTransferParameters*. After the structure is initialized, it can be reused as many times as needed without being reinitialized.

*TransferBuffer* is an optional pointer into which *SpbRequestGetTransferParameters* writes a pointer to an MDL that describes the physical page layout for the transfer buffer. The transfer buffer can be described by a single MDL or by an MDL chain. A simple buffer, which consists of a contiguous block of virtual memory, is described by a single MDL. If a transfer buffer is formatted as a scatter-gather list, each contiguous block of virtual memory in the buffer is described by an MDL in an MDL chain. For more information about MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

### Examples

```cpp
//
// Note that this snippet shows a transfer completing synchronously. This
// is a horrible thing for a driver to do, but demonstrates the DDI nicely.
//

WDF_REQUEST_PARAMETERS parameters;
WDF_TRANSFER_DESCRIPTOR transfer;

WDF_REQUEST_PARAMETERS_INIT(&parameters);
WDF_TRANSFER_DESCRIPTOR_INIT(&transfer);

SpbRequestGetParameters(request, &parameters);

for (ULONG i = 0; i < parameters.SequenceCount; i += 1)
{
    WDFMEMORY buffer;

    SpbRequestGetTransferParameters(request, i, &transfer, &buffer);

    MyDriverPerformTransfer(deviceContext, 
                            request,
                            transfer,
                            buffer);
}
```

## -see-also

* [IOCTL_SPB_EXECUTE_SEQUENCE](/windows-hardware/drivers/spb/spb-ioctls#ioctl_spb_execute_sequence)
* [SPBREQUEST](/windows-hardware/drivers/spb/spbcx-object-handles)
* [SPB_TRANSFER_DESCRIPTOR](./ns-spbcx-spb_transfer_descriptor.md)
* [SPB_TRANSFER_DESCRIPTOR_INIT](./nf-spbcx-spb_transfer_descriptor_init.md)
* [SpbRequestGetParameters](./nf-spbcx-spbrequestgetparameters.md)