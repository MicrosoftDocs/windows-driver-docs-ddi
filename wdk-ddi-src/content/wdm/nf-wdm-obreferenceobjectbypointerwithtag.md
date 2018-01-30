---
UID: NF:wdm.ObReferenceObjectByPointerWithTag
title: ObReferenceObjectByPointerWithTag function
author: windows-driver-content
description: The ObReferenceObjectByPointerWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing.
old-location: kernel\obreferenceobjectbypointerwithtag.htm
old-project: kernel
ms.assetid: eaa730a8-8ee3-43a7-a18e-094fbac4ba60
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ObReferenceObjectByPointerWithTag, k107_5e5e16de-36ff-4a81-9fe6-9602053ccc6b.xml, ObReferenceObjectByPointerWithTag routine [Kernel-Mode Driver Architecture], wdm/ObReferenceObjectByPointerWithTag, kernel.obreferenceobjectbypointerwithtag
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObReferenceObjectByPointerWithTag
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObReferenceObjectByPointerWithTag function


## -description


The <b>ObReferenceObjectByPointerWithTag</b> routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support <a href="http://go.microsoft.com/fwlink/p/?linkid=153590">object reference tracing</a>.


## -syntax


````
NTSTATUS ObReferenceObjectByPointerWithTag(
  _In_     PVOID           Object,
  _In_     ACCESS_MASK     DesiredAccess,
  _In_opt_ POBJECT_TYPE    ObjectType,
  _In_     KPROCESSOR_MODE AccessMode,
  _In_     ULONG           Tag
);
````


## -parameters




### -param Object [in]

A pointer to the object. The caller obtains this pointer either when it creates the object, or from a previous call to the <a href="..\wdm\nf-wdm-obreferenceobjectbyhandlewithtag.md">ObReferenceObjectByHandleWithTag</a> routine after it opens the object.


### -param DesiredAccess [in]

Specifies the types of access to the object that the caller requests. This parameter is a bitmask of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>. The interpretation of this field depends on the object type. Do not use any generic access rights.


### -param ObjectType [in, optional]

A pointer to an opaque structure that specifies the object type. This parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558675">OBJECT_TYPE</a> structure. Set <i>ObjectType</i> to <b>NULL</b> or to one of the following pointer values, which are declared in the Wdm.h header file: <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsProcessType</b>, <b>*PsThreadType</b>, <b>*SeTokenObjectType</b>, <b>*TmEnlistmentObjectType</b>, <b>*TmResourceManagerObjectType</b>, <b>*TmTransactionManagerObjectType</b>, or <b>*TmTransactionObjectType</b>. This parameter can be <b>NULL</b> if <i>AccessMode</i> is <b>KernelMode</b>. If <i>ObjectType</i> is not <b>NULL</b>, the routine verifies that the supplied object type matches the object type of the object that the <i>Handle</i> parameter specifies.


### -param AccessMode [in]

Indicates the access mode to use for the access check. Set this parameter to one of the following <b>MODE</b> enumeration values:
<ul>
<li>
<b>UserMode</b>

</li>
<li>
<b>KernelMode</b>

</li>
</ul>Lower-level drivers should specify <b>KernelMode</b>.


### -param Tag [in]

Specifies a four-byte, custom tag value. For more information, see the following Remarks section.


## -returns


<b>ObReferenceObjectByPointerWithTag</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:
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
The <i>ObjectType</i> parameter specifies the wrong object type for the object that the <i>Object</i> parameter points to, or <i>ObjectType</i> is <b>NULL</b> but <i>AccessMode</i> is <b>UserMode</b>.

</td>
</tr>
</table> 



## -remarks


This routine does access validation of the specified object. If access can be granted, the routine increments the object reference count. This increment prevents the object from being deleted while the caller uses the object. When the object is no longer needed, the caller should decrement the reference count by calling the <a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a> or <a href="..\wdm\nf-wdm-obdereferenceobjectdeferdeletewithtag.md">ObDereferenceObjectDeferDeleteWithTag</a> routine.

For more information about object references, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554294">Life Cycle of an Object</a>.

The <a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a> routine is similar to <b>ObReferenceObjectByPointerWithTag</b>, except that it does not enable the caller to write a custom tag to an object. In Windows 7 and later versions of Windows, <b>ObReferenceObjectByPointer</b> always writes a default tag value ('tlfD') to the object. A call to <b>ObReferenceObjectByPointer</b> has the same effect as a call to <b>ObReferenceObjectByPointerWithTag</b> that specifies <i>Tag</i> = 'tlfD'.

To view an object reference trace in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153599">Windows debugging tools</a>, use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> kernel-mode debugger extension. In Windows 7, the <a href="http://go.microsoft.com/fwlink/p/?linkid=153600">!obtrace</a> extension is enhanced to display object reference tags, if object reference tracing is enabled. By default, object reference tracing is turned off. Use the <a href="http://go.microsoft.com/fwlink/p/?linkid=153601">Global Flags Editor</a> (Gflags) to enable object reference tracing. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558668">Object Reference Tracing with Tags</a>.



## -see-also

<a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a>

<a href="..\wdm\nf-wdm-obdereferenceobjectdeferdeletewithtag.md">ObDereferenceObjectDeferDeleteWithTag</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

<a href="..\wdm\nf-wdm-obdereferenceobjectwithtag.md">ObDereferenceObjectWithTag</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558675">OBJECT_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectByPointerWithTag routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

