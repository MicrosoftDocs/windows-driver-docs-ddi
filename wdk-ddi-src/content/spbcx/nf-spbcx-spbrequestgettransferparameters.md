---
UID: NF:spbcx.SpbRequestGetTransferParameters
title: SpbRequestGetTransferParameters function (spbcx.h)
description: The SpbRequestGetTransferParameters method retrieves the transfer parameters for an individual transfer in an I/O transfer sequence.
old-location: spb\spbrequestgettransferparameters.htm
tech.root: SPB
ms.assetid: 33B0C9EF-B40A-4BE7-A5AB-81FFF4698F3F
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

The <b>SpbRequestGetTransferParameters</b> method retrieves the transfer parameters for an individual transfer in an <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/i-o-transfer-sequences">I/O transfer sequence</a>.

## -parameters

### -param SpbRequest 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request from which to retrieve the transfer parameters. This parameter must be a handle to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> request.

### -param Index 

[in]
The index of a transfer in the I/O transfer sequence. For more information, see the following Remarks section.

### -param TransferDescriptor 

[out, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor">SPB_TRANSFER_DESCRIPTOR</a> structure into which  the method writes the transfer parameters. The <i>TransferDescriptor</i> parameter is optional and can be specified as NULL if the caller does not require the transfer parameters. For more information, see the following Remarks section.

### -param TransferBuffer 

[out, optional]
A pointer to a location into which the method writes a pointer to an MDL (or an MDL chain) that describes the physical memory in the transfer buffer.  The caller must not modify the contents of this MDL. This parameter is optional and can be set to NULL if the MDL is not needed. For more information, see the following Remarks section.

## -remarks

To request an I/O transfer sequence, a client (peripheral driver) of the SPB controller driver sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> request that contains a list of the transfers in the sequence. Your controller driver can call <b>SpbRequestGetTransferParameters</b> to obtain information about a particular transfer in the sequence.

The <i>Index</i> parameter is an index that identifies a particular transfer in the sequence.   If N is the number of transfers in the sequence, valid indexes range from 0 to N–1. To determine the number of transfers in the sequence, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a> method. This method retrieves an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor">SPB_TRANSFER_DESCRIPTOR</a> structure that contains the request parameters. The <b>TransferCount</b> member of this structure specifies the number of transfers in the sequence.

If <i>TransferDescriptor</i> is non-NULL, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_transfer_descriptor_init">SPB_TRANSFER_DESCRIPTOR_INIT</a> function to initialize the structure before calling  <b>SpbRequestGetTransferParameters</b>.  After the structure is initialized, it can be reused as many times as needed without being reinitialized.

<i>TransferBuffer</i> is an optional pointer into which <b>SpbRequestGetTransferParameters</b> writes a pointer to an MDL that describes the physical page layout for the transfer buffer. The transfer buffer can be described by a single MDL or by an MDL chain. A simple buffer, which consists of a contiguous block of virtual memory, is described by a single MDL. If a transfer buffer is formatted as a scatter-gather list, each contiguous block of virtual memory in the buffer is described by an MDL in an MDL chain. For more information about MDLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.


#### Examples


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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-spb_transfer_descriptor">SPB_TRANSFER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_transfer_descriptor_init">SPB_TRANSFER_DESCRIPTOR_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spbrequestgetparameters">SpbRequestGetParameters</a>

