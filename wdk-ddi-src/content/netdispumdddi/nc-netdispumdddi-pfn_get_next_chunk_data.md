---
UID: NC:netdispumdddi.PFN_GET_NEXT_CHUNK_DATA
title: PFN_GET_NEXT_CHUNK_DATA (netdispumdddi.h)
description: Provides info about the next Miracast encode chunk that was reported to the Microsoft DirectX graphics kernel subsystem when the DXGK_INTERRUPT_TYPE interrupt type is DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE.The data type of this function is PFN_GET_NEXT_CHUNK_DATA.
old-location: display\getnextchunkdata.htm
tech.root: display
ms.assetid: 24b1d89a-4200-41ec-aa73-15b37e4cca6d
ms.date: 05/10/2018
keywords: ["PFN_GET_NEXT_CHUNK_DATA callback function"]
ms.keywords: GetNextChunkData, GetNextChunkData callback function [Display Devices], PFN_GET_NEXT_CHUNK_DATA, PFN_GET_NEXT_CHUNK_DATA callback, display.getnextchunkdata, netdispumdddi/GetNextChunkData
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFN_GET_NEXT_CHUNK_DATA
 - netdispumdddi/PFN_GET_NEXT_CHUNK_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Netdispumdddi.h
api_name:
 - GetNextChunkData
---

# PFN_GET_NEXT_CHUNK_DATA callback function


## -description

Provides info about the next Miracast encode chunk that was reported to the Microsoft DirectX graphics kernel subsystem when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a> interrupt type is  <b>DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE</b>.The data type of this function is <b>PFN_GET_NEXT_CHUNK_DATA</b>.

## -parameters

### -param hMiracastDeviceHandle 

[in]
A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.

### -param TimeoutInMilliseconds 

[in]
The timeout interval value, in milliseconds, supplied by the Miracast user-mode driver.

If this value is <b>INFINITE</b>, the operating system blocks calls to <b>GetNextChunkData</b> until a chunk becomes available.

If this value is zero and a chunk is not ready, the operating system will not block a call to <b>GetNextChunkData</b>.

### -param AdditionalWaitEventCount 

[in]
The number of additional events that are supplied in the <i>pAdditionalWaitEvents</i> parameter.

A maximum of 4 wait events can be supplied.

### -param pAdditionalWaitEvents 

[in, optional]
An optional pointer to an array of events that  <b>GetNextChunkData</b> will wait on while waiting for a new encode chunk.

### -param pChunkDataBufferSize 

[in, out]
A pointer to a variable that contains the size, in bytes, of the <i>pChunkDataBuffer</i> buffer.

When <b>GetNextChunkData</b> is called, this parameter contains the size of <i>pChunkDataBuffer</i>.

When  <b>GetNextChunkData</b> returns a success code, this parameter contains the size of actual encode chunk data returned in <i>pChunkDataBuffer</i>.

### -param pChunkDataBuffer 

[out]
A pointer to a buffer of type  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_data">MIRACAST_CHUNK_DATA</a> that the operating system provides to store information about the next encode chunk. This parameter is provided only if the call to <b>GetNextChunkData</b> is successful.

### -param pOutstandingChunksToProcess 

[out]
A pointer to a variable that contains the number of outstanding encode chunks that are available for the driver at the time this call returned.  This parameter is provided only if the call to <b>GetNextChunkData</b> is successful.

Note that as chunks are completed by the GPU asynchronously, this parameter only gives an indication of the number of outstanding chunks.

## -returns

If info on an encode chunk was returned successfully, the <b>STATUS_SUCCESS</b> status code is returned, and the value of *<i>pChunkDataBufferSize</i> is non-zero.

These additional status codes can be returned:

## -remarks

This function is optional. The user-mode display driver should only call it if the display miniport driver responds to  interrupts from the GPU when the GPU completes the encoding of a chunk by passing data in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_data">MIRACAST_CHUNK_DATA</a>.<b>PrivateDriverData</b> member at that interrupt time.

The user-mode display driver can use the sizes of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_data">MIRACAST_CHUNK_DATA</a> structure and the <b>MIRACAST_CHUNK_DATA</b>.<b>PrivateDriverData</b> member to compute the size of a chunk and hence how to move from chunk to chunk in the returned buffer.

In a call to this function, as many available packets as can fit will be placed sequentially in the supplied buffer. This code snippet shows how to calculate the size of each packet:

```cpp
ChunkSize == FIELD_OFFSET
    (D3DKMT_MIRACAST_CHUNK_DATA, PrivateDriverData) \
    + Chunk->ChunkData.PrivateDriverDataSize;
```

#### Thread Safety

Only one thread should call this function at a time. Otherwise it's unpredictable which call would receive chunk info and which call would fail.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/ns-netdispumdddi-miracast_chunk_data">MIRACAST_CHUNK_DATA</a>

