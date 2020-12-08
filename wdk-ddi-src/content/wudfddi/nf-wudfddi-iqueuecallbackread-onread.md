---
UID: NF:wudfddi.IQueueCallbackRead.OnRead
title: IQueueCallbackRead::OnRead (wudfddi.h)
description: The OnRead method is called to handle a read request when an application reads information from a device through the Microsoft Win32 ReadFile or ReadFileEx function.
old-location: wdf\iqueuecallbackread_onread.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IQueueCallbackRead::OnRead"]
ms.keywords: IQueueCallbackRead interface,OnRead method, IQueueCallbackRead.OnRead, IQueueCallbackRead::OnRead, OnRead, OnRead method, OnRead method,IQueueCallbackRead interface, UMDFQueueObjectRef_56f5bb6c-4b65-4ab9-961a-278bfc6dbfe9.xml, umdf.iqueuecallbackread_onread, wdf.iqueuecallbackread_onread, wudfddi/IQueueCallbackRead::OnRead
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackRead::OnRead
 - wudfddi/IQueueCallbackRead::OnRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackRead.OnRead
---

# IQueueCallbackRead::OnRead


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnRead</b> method is called to handle a read request when an application reads information from a device through the Microsoft Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function.

## -parameters

### -param pWdfQueue 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from.

### -param pWdfRequest 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface that represents the framework request object.

### -param NumOfBytesToRead 

[in]
The size, in bytes, of the read buffer for the request.

## -remarks

A driver registers the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackread">IQueueCallbackRead</a> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single <b>OnRead</b> method for all I/O queues or separate <b>OnRead</b> methods for each I/O queue. 

The <b>OnRead</b> method receives every read request type from the queue. (The read request type is identified by the <b>WdfRequestRead</b> value of the <a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a> enumeration type for the request.) The <b>OnRead</b> method must process each received read request. For more information about how UMDF drivers process I/O requests, see <a href="/windows-hardware/drivers/wdf/processing-i-o-requests">Processing I/O Requests</a>.

The driver can call the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getreadparameters">IWDFIoRequest::GetReadParameters</a> and <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a> methods to retrieve information about the request and the read buffer.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackread">IQueueCallbackRead</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>
