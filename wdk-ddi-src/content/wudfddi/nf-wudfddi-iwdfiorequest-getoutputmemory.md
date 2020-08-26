---
UID: NF:wudfddi.IWDFIoRequest.GetOutputMemory
title: IWDFIoRequest::GetOutputMemory (wudfddi.h)
description: The GetOutputMemory method retrieves the memory object that represents the output buffer for an I/O request.
old-location: wdf\iwdfiorequest_getoutputmemory.htm
tech.root: wdf
ms.assetid: 12862fb2-4cdb-4446-aa20-ec911c9cd65f
ms.date: 02/26/2018
keywords: ["IWDFIoRequest::GetOutputMemory"]
ms.keywords: GetOutputMemory, GetOutputMemory method, GetOutputMemory method,IWDFIoRequest interface, IWDFIoRequest interface,GetOutputMemory method, IWDFIoRequest.GetOutputMemory, IWDFIoRequest::GetOutputMemory, UMDFRequestObjectRef_618a405c-a272-4427-809b-46b7f46b75de.xml, umdf.iwdfiorequest_getoutputmemory, wdf.iwdfiorequest_getoutputmemory, wudfddi/IWDFIoRequest::GetOutputMemory
f1_keywords:
 - "wudfddi/IWDFIoRequest.GetOutputMemory"
 - "IWDFIoRequest.GetOutputMemory"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest.GetOutputMemory
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetOutputMemory


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetOutputMemory</b> method retrieves the memory object that represents the output buffer for an I/O request.


## -parameters




### -param ppWdfMemory 
[out]
A pointer to a variable that receives a pointer to the reference-counted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for the memory object. Note that returning <b>NULL</b> is valid; in this situation, no output memory is associated with the I/O request.


## -remarks



Drivers that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> access method can call <b>GetOutputMemory</b> to obtain an I/O request's output buffer.

Before a driver completes an I/O request, the driver must call the <b>IWDFMemory::Release</b> method for the memory object. The underlying memory object is freed when the request is completed.

The output buffer that is associated with the I/O request contains information (for example, data from a disk) that the driver provides to the originator of the request. The driver can call <b>GetOutputMemory</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data). To access the output buffer, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfmemory-getdatabuffer">IWDFMemory::GetDataBuffer</a> method.

UMDF creates an I/O request's memory objects when it receives the I/O request, before it adds the I/O request to a driver's I/O queue. If UMDF cannot allocate memory for the memory objects, it completes the I/O request with a failure return status and does not deliver the I/O request to the driver.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

For a code example of how to use the <b>GetOutputMemory</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfmemory-getdatabuffer">IWDFMemory::GetDataBuffer</a>
 

 

