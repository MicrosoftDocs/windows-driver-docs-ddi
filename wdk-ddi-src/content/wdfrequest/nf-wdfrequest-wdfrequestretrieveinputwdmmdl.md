---
UID: NF:wdfrequest.WdfRequestRetrieveInputWdmMdl
title: WdfRequestRetrieveInputWdmMdl function
author: windows-driver-content
description: The WdfRequestRetrieveInputWdmMdl method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.
old-location: wdf\wdfrequestretrieveinputwdmmdl.htm
old-project: wdf
ms.assetid: 8046d9e4-d4a2-4aeb-92b2-a48277af8b41
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestRetrieveInputWdmMdl method, PFN_WDFREQUESTRETRIEVEINPUTWDMMDL, wdfrequest/WdfRequestRetrieveInputWdmMdl, DFRequestObjectRef_d65a1869-de52-4284-818f-a3f0837d0374.xml, wdf.wdfrequestretrieveinputwdmmdl, kmdf.wdfrequestretrieveinputwdmmdl, WdfRequestRetrieveInputWdmMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfRequestRetrieveInputWdmMdl
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveInputWdmMdl function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.


## -syntax


````
NTSTATUS WdfRequestRetrieveInputWdmMdl(
  _In_  WDFREQUEST Request,
  _Out_ PMDL       *Mdl
);
````


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Mdl [out]

A pointer to a location that receives a pointer to an MDL.


## -returns


<b>WdfRequestRetrieveInputWdmMdl</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request type is not valid or the request is using <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The input buffer's length is zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
</table> 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.



## -remarks


A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputWdmMdl</b> for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves the input buffer's MDL for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputWdmMdl</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveInputWdmMdl</b> returns STATUS_SUCCESS, the driver receives a pointer to an MDL that describes the input buffer. 

The driver must not access a request's MDL after <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completing the I/O request</a>.

For more information about <b>WdfRequestRetrieveInputWdmMdl</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveInputWdmMdl method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

