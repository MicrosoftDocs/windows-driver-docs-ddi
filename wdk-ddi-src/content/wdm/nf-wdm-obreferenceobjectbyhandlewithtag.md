---
UID: NF:wdm.ObReferenceObjectByHandleWithTag
title: ObReferenceObjectByHandleWithTag function
author: windows-driver-content
description: The ObReferenceObjectByHandleWithTag routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectbyhandlewithtag.htm
old-project: kernel
ms.assetid: f36beac8-e4fb-49ce-b49d-a1a8f32f19a5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ObReferenceObjectByHandleWithTag, ObReferenceObjectByHandleWithTag, k107_431c6c60-e2bd-4d90-9054-b950195bbec3.xml, ObReferenceObjectByHandleWithTag routine [Kernel-Mode Driver Architecture], kernel.obreferenceobjectbyhandlewithtag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObReferenceObjectByHandleWithTag
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObReferenceObjectByHandleWithTag function


## -description


The <b>ObReferenceObjectByHandleWithTag</b> routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>. 


## -syntax


````
NTSTATUS ObReferenceObjectByHandleWithTag(
  _In_      HANDLE                     Handle,
  _In_      ACCESS_MASK                DesiredAccess,
  _In_opt_  POBJECT_TYPE               ObjectType,
  _In_      KPROCESSOR_MODE            AccessMode,
  _In_      ULONG                      Tag,
  _Out_     PVOID                      *Object,
  _Out_opt_ POBJECT_HANDLE_INFORMATION HandleInformation
);
````


## -parameters




### -param Handle [in]

Specifies an open handle for an object. 


### -param DesiredAccess [in]

Specifies the types of access to the object that the caller requests. This parameter is a bitmask of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>. The interpretation of this field depends on the object type. Do not use any generic access rights. 


### -param ObjectType [in, optional]

A pointer to an opaque structure that specifies the object type. This parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558675">OBJECT_TYPE</a> structure. Set <i>ObjectType</i> to <b>NULL</b> or to one of the following pointer values, which are declared in the Wdm.h header file: <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsProcessType</b>, <b>*PsThreadType</b>, <b>*SeTokenObjectType</b>, <b>*TmEnlistmentObjectType</b>, <b>*TmResourceManagerObjectType</b>, <b>*TmTransactionManagerObjectType</b>, or <b>*TmTransactionObjectType</b>. If <i>ObjectType</i> is not <b>NULL</b>, the routine verifies that the supplied object type matches the object type of the object that the <i>Handle</i> parameter specifies. 


### -param AccessMode [in]

Specifies the access mode to use for the access check. It must be either <b>UserMode</b> or <b>KernelMode</b>. Drivers should always specify <b>UserMode</b> for handles they receive from user address space.


### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.


### -param Object [out]

A pointer to a variable into which the routine writes a pointer to the object. The following table lists the <i>Object</i> pointer types that are designated by the possible <i>ObjectType</i> parameter values.

<table>
<tr>
<th><i>ObjectType</i> parameter</th>
<th><i>Object </i>pointer type</th>
</tr>
<tr>
<td>
<b>*ExEventObjectType</b>

</td>
<td>
PKEVENT

</td>
</tr>
<tr>
<td>
<b>*ExSemaphoreObjectType</b>

</td>
<td>
PKSEMAPHORE

</td>
</tr>
<tr>
<td>
<b>*IoFileObjectType</b>

</td>
<td>
PFILE_OBJECT

</td>
</tr>
<tr>
<td>
<b>*PsProcessType</b>

</td>
<td>
PEPROCESS or PKPROCESS

</td>
</tr>
<tr>
<td>
<b>*PsThreadType</b>

</td>
<td>
PETHREAD or PKTHREAD

</td>
</tr>
<tr>
<td>
<b>*SeTokenObjectType</b>

</td>
<td>
PACCESS_TOKEN

</td>
</tr>
<tr>
<td>
<b>*TmEnlistmentObjectType</b>

</td>
<td>
PKENLISTMENT

</td>
</tr>
<tr>
<td>
<b>*TmResourceManagerObjectType</b>

</td>
<td>
PKRESOURCEMANAGER

</td>
</tr>
<tr>
<td>
<b>*TmTransactionManagerObjectType</b>

</td>
<td>
PKTM

</td>
</tr>
<tr>
<td>
<b>*TmTransactionObjectType</b>

</td>
<td>
PKTRANSACTION

</td>
</tr>
</table>
 

The structures that the pointer types reference are opaque, and drivers cannot access the structure members. Because the structures are opaque, PEPROCESS is equivalent to PKPROCESS, and PETHREAD is equivalent to PKTHREAD. 


### -param HandleInformation [out, optional]

Drivers set this parameter to <b>NULL</b>. 


## -returns



<b>ObReferenceObjectByHandleWithTag</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectType</i> parameter specifies the wrong object type for the object that is identified by the <i>Handle</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the required access rights to the object. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not valid. 

</td>
</tr>
</table>
 




## -remarks



This routine does access validation of the specified object handle. If access can be granted, the routine increments the object reference count and provides an object pointer to the caller. This increment prevents the object from being deleted while the caller uses the object. When the object is no longer needed, the caller should decrement the reference count by calling the <a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a> or <a href="..\wdm\nf-wdm-obdereferenceobjectdeferdeletewithtag.md">ObDereferenceObjectDeferDeleteWithTag</a> routine.

For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.

<b>ObReferenceObjectByHandleWithTag</b> does not close or invalidate the object handle that is specified by the <i>Handle</i> parameter. When the handle is no longer needed, the caller can close the handle by calling the <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> routine.

If the <i>AccessMode</i> parameter value is <b>KernelMode</b>, the requested access is always allowed. If <i>AccessMode</i> is <b>UserMode</b>, the requested access is compared to the access rights that the caller has to the object. Only highest-level drivers can safely specify the <b>UserMode</b> value for the <i>AccessMode</i> parameter.

Starting with Windows 7, if <i>AccessMode</i> is <b>KernelMode</b> and handle is received from user address space, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> issues bugcheck C4, subcode F6.

The <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> routine is similar to <b>ObReferenceObjectByHandleWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObReferenceObjectByHandle</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObReferenceObjectByHandle</b> has the same effect as a call to <b>ObReferenceObjectByHandleWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>. 




## -see-also

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558675">OBJECT_TYPE</a>



<a href="..\wdm\nf-wdm-obdereferenceobjectdeferdeletewithtag.md">ObDereferenceObjectDeferDeleteWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectByHandleWithTag routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

