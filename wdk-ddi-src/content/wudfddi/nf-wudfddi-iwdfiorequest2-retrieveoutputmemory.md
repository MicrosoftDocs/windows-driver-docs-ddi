---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveOutputMemory
title: IWDFIoRequest2::RetrieveOutputMemory method
author: windows-driver-content
description: The RetrieveOutputMemory method retrieves the IWDFMemory interface of a framework memory object that represents an I/O request's output buffer.
old-location: wdf\iwdfiorequest2_retrieveoutputmemory.htm
old-project: wdf
ms.assetid: d17e7435-adc3-4248-a6c9-c7e267504291
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoRequest2, RetrieveOutputMemory, umdf.iwdfiorequest2_retrieveoutputmemory, wdf.iwdfiorequest2_retrieveoutputmemory, UMDFRequestObjectRef_9fbbb5ad-480f-4744-805a-1af1dd841274.xml, IWDFIoRequest2 interface, RetrieveOutputMemory method, IWDFIoRequest2::RetrieveOutputMemory, RetrieveOutputMemory method, IWDFIoRequest2 interface, wudfddi/IWDFIoRequest2::RetrieveOutputMemory, RetrieveOutputMemory method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest2.RetrieveOutputMemory
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest2::RetrieveOutputMemory method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveOutputMemory</b> method retrieves the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.


## -syntax


````
HRESULT RetrieveOutputMemory(
  [out] IWDFMemory **Memory
);
````


## -parameters




### -param Memory [out]

The address of a location that receives a pointer to the <b>IWDFMemory</b> interface of a UMDF memory object.


## -returns


<b>RetrieveOutputMemory</b> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT_BUFFER)</b></dt>
</dl>
</td>
<td width="60%">
The I/O request did not provide an input buffer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Not enough memory is available to retrieve the buffer. The driver should complete the request with an error status value.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.







## -remarks


A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <b>RetrieveOutputMemory</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <b>RetrieveOutputMemory</b> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <b>RetrieveOutputMemory</b> returns S_OK, the driver receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of a UMDF memory object that represents the output buffer. To access the buffer, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>. 

The driver can access the retrieved framework memory object until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request. Before the driver completes the I/O request, it must call <b>IWDFMemory::Release</b>. 

Instead of calling <b>RetrieveOutputMemory</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>, which retrieves the buffer's address and length.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::RetrieveOutputMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

