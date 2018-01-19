---
UID: NF:wudfddi.IQueueCallbackWrite.OnWrite
title: IQueueCallbackWrite::OnWrite method
author: windows-driver-content
description: The OnWrite method is called to handle a write request when an application writes information to a device through the Microsoft Win32 WriteFile or WriteFileEx function.
old-location: wdf\iqueuecallbackwrite_onwrite.htm
old-project: wdf
ms.assetid: a87a9976-f844-4e69-82d3-2d426e359763
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IQueueCallbackWrite, IQueueCallbackWrite::OnWrite, OnWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IQueueCallbackWrite.OnWrite
req.alt-loc: Wudfddi.h
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackWrite::OnWrite method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnWrite</b> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 



## -syntax

````
void  OnWrite(
  [in] IWDFIoQueue   *pWdfQueue,
  [in] IWDFIoRequest *pWdfRequest,
  [in] SIZE_T        NumOfBytesToWrite
);
````


## -parameters

### -param pWdfQueue [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from. 


### -param pWdfRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object. 


### -param NumOfBytesToWrite [in]

The size, in bytes, of the write buffer for the request.


## -returns
None


## -remarks
A driver registers the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

A driver can implement a single <b>OnWrite</b> method for all I/O queues or separate <b>OnWrite</b> methods for each I/O queue. 

The <b>OnWrite</b> method receives every write request type from the queue. (The write request type is identified by the <b>WdfRequestWrite</b> value of the <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a> enumeration type for the request.) The <b>OnWrite</b> method must process each received write request. For more information about how UMDF drivers process I/O requests, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559130">IWDFIoRequest::GetWriteParameters</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> methods to retrieve information about the request and the write buffer.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackWrite::OnWrite method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

