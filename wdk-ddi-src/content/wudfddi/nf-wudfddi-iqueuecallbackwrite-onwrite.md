---
UID: NF:wudfddi.IQueueCallbackWrite.OnWrite
title: IQueueCallbackWrite::OnWrite (wudfddi.h)
description: The OnWrite method is called to handle a write request when an application writes information to a device through the Microsoft Win32 WriteFile or WriteFileEx function.
old-location: wdf\iqueuecallbackwrite_onwrite.htm
tech.root: wdf
ms.assetid: a87a9976-f844-4e69-82d3-2d426e359763
ms.date: 02/26/2018
keywords: ["IQueueCallbackWrite::OnWrite"]
ms.keywords: IQueueCallbackWrite interface,OnWrite method, IQueueCallbackWrite.OnWrite, IQueueCallbackWrite::OnWrite, OnWrite, OnWrite method, OnWrite method,IQueueCallbackWrite interface, UMDFQueueObjectRef_77d33d9d-856e-4b3b-818d-37b0ad6889a7.xml, umdf.iqueuecallbackwrite_onwrite, wdf.iqueuecallbackwrite_onwrite, wudfddi/IQueueCallbackWrite::OnWrite
f1_keywords:
 - "wudfddi/IQueueCallbackWrite.OnWrite"
 - "IQueueCallbackWrite.OnWrite"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IQueueCallbackWrite.OnWrite
targetos: Windows
req.typenames: 
---

# IQueueCallbackWrite::OnWrite


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnWrite</b> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 


## -parameters




### -param pWdfQueue 
[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from. 


### -param pWdfRequest 
[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface that represents the framework request object. 


### -param NumOfBytesToWrite 
[in]
The size, in bytes, of the write buffer for the request.


## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackwrite">IQueueCallbackWrite</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single <b>OnWrite</b> method for all I/O queues or separate <b>OnWrite</b> methods for each I/O queue. 

The <b>OnWrite</b> method receives every write request type from the queue. (The write request type is identified by the <b>WdfRequestWrite</b> value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a> enumeration type for the request.) The <b>OnWrite</b> method must process each received write request. For more information about how UMDF drivers process I/O requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

The driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getwriteparameters">IWDFIoRequest::GetWriteParameters</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a> methods to retrieve information about the request and the write buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackwrite">IQueueCallbackWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>
 

 

