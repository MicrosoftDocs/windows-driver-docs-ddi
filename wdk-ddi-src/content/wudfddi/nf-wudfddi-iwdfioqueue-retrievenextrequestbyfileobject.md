---
UID: NF:wudfddi.IWDFIoQueue.RetrieveNextRequestByFileObject
title: IWDFIoQueue::RetrieveNextRequestByFileObject
author: windows-driver-content
description: The RetrieveNextRequestByFileObject method retrieves from an I/O queue the next I/O request whose file object matches the specified file object.
old-location: wdf\iwdfioqueue_retrievenextrequestbyfileobject.htm
old-project: wdf
ms.assetid: 136b7582-b974-44fb-8026-e9678ae6623c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoQueue interface,RetrieveNextRequestByFileObject method, IWDFIoQueue.RetrieveNextRequestByFileObject, IWDFIoQueue::RetrieveNextRequestByFileObject, RetrieveNextRequestByFileObject, RetrieveNextRequestByFileObject method, RetrieveNextRequestByFileObject method,IWDFIoQueue interface, UMDFQueueObjectRef_15af6c6e-0a40-41bd-9b76-fb7c206bc937.xml, umdf.iwdfioqueue_retrievenextrequestbyfileobject, wdf.iwdfioqueue_retrievenextrequestbyfileobject, wudfddi/IWDFIoQueue::RetrieveNextRequestByFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoQueue.RetrieveNextRequestByFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::RetrieveNextRequestByFileObject


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveNextRequestByFileObject</b> method retrieves from an I/O queue the next I/O request whose file object matches the specified file object.


## -parameters




### -param pFile




### -param ppRequest [out]

A pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface for the next request object whose file object matches the supplied file object, or receives <b>NULL</b> if the queue is empty or if the next request is not found.


#### - pFileObject [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object that is used to retrieve the next I/O request whose file object matches this supplied file object. 


## -returns



<b>RetrieveNextRequestByFileObject</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The next I/O request was successfully retrieved from the I/O queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_WDF_PAUSED)</b></dt>
</dl>
</td>
<td width="60%">
The queue is not dispatching requests. This situation occurs if the device undergoes a power state transition and all of the queues are stopped from dispatching requests or if the driver explicitly called <a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a> to stop dispatching requests. This situation can also occur if the driver attempts to remove a request from a manual queue that is power managed and that is powered down or if the queue is paused.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NO_MORE_ITEMS)</b></dt>
</dl>
</td>
<td width="60%">
No requests were in the queue.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>
</td>
<td width="60%">
The call was made to retrieve the request from a parallel queue.

</td>
</tr>
</table>
 

<b>RetrieveNextRequestByFileObject</b> might also return other HRESULT values.




## -remarks



If a driver configures an I/O queue for manual dispatching of I/O requests, the driver can call the <b>RetrieveNextRequestByFileObject</b> method to obtain the next request whose file object matches the supplied file object from the queue. For more information about manually dispatching I/O requests, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">Configuring Dispatch Mode for an I/O Queue</a>. 

If multiple I/O requests whose file objects match the file object that the <i>pFileObject</i> parameter points to exist in the I/O queue, the first I/O request is returned.


#### Examples

For a code example of how to use the <b>RetrieveNextRequestByFileObject</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>
 

 

