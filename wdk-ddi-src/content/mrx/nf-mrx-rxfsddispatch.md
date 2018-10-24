---
UID: NF:mrx.RxFsdDispatch
title: RxFsdDispatch function
author: windows-driver-content
description: RxFsdDispatch implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP).
old-location: ifsk\rxfsddispatch.htm
tech.root: ifsk
ms.assetid: 92b9b22a-0fe7-4c95-a4fc-5f5f5558b4cf
ms.date: 04/16/2018
ms.keywords: RxFsdDispatch, RxFsdDispatch routine [Installable File System Drivers], ifsk.rxfsddispatch, mrx/RxFsdDispatch, rxref_23ec1489-9629-4aef-b0b0-d844364b67a7.xml
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h, Rxstruc.h, Struchdr.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrx.h
api_name:
-	RxFsdDispatch
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxFsdDispatch function


## -description


<b>RxFsdDispatch</b> implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP). A pointer to this routine is copied over the device driver dispatch table for the network mini-redirector driver by the <b>RxDriverEntry</b> routine when RDBSS is initialized. 


## -parameters




### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network mini-redirector.


### -param Irp [in]

A pointer to the I/O request packet being processed.


## -returns



<b>RxFsdDispatch</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
A request was made on an invalid device object. For example, this error is returned if a file system object is passed as the <i>RxDeviceObject</i> parameter. This status value indicates failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
An invalid request was made to create a named pipe or a mailslot (the <b>MajorFunction</b> member of the <i>Irp</i> was IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE). This status value indicates failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An asynchronous request was made and the status of the request is pending.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The <b>RxFsdDispatch</b> routine call was successful.

</td>
</tr>
</table>
 




## -remarks



<b>RxFsdDispatch</b> is called by RDBSS to process an I/O request packet (IRP). These IRPs are normally received by RDBSS in response to a user-mode application requesting operations on a file. It is also possible for another kernel driver to issue such an IRP. 

A pointer to <b>RxFsdDispatch</b> routine is copied over the driver dispatch table for a network mini-redirector driver when the <b>RxDriverEntry</b> routine is called to initialize RDBSS. 

Internally, RDBSS maintains two dispatch vectors:

<ul>
<li>
A common dispatch vector for most operations.

</li>
<li>
A private dispatch vector for file device FCB operations.

</li>
</ul>
If the IRP is an IRP_MJ_CREATE request, then <b>RxFsdDispatch</b> will use a common dispatch vector. If the IRP is for an operation on an FCB of a file object, <b>RxFsdDispatch</b> will check if a private dispatch vector should be used. Otherwise a common dispatch vector will be used to process the IRP. 

<b>RxFsdDispatch</b> calls internal routines to process the standard IRPs most of which result in a call to one of the callback routines implemented by the network mini-redirector driver. 

A few IRPs are treated as special and handled internally by RDBSS. For example, the IRP_MJ_SYSTEM_CONTROL is used internally if WMI is enabled. IRP_MJ_CREATE_MAILSLOT or IRP_MJ_CREATE_NAMED_PIPE requests are treated specially and rejected (a STATUS_OBJECT_NAME_INVALID error is returned). 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554404">RxDriverEntry</a>
 

 

