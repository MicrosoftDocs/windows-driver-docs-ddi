---
UID: NF:wdm.ObReferenceObjectByPointer
title: ObReferenceObjectByPointer function
author: windows-driver-content
description: The ObReferenceObjectByPointer routine increments the pointer reference count for a given object.
old-location: kernel\obreferenceobjectbypointer.htm
old-project: kernel
ms.assetid: c575bd3f-6790-4815-b7c7-8ee16a9cac17
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, O, ObReferenceObjectByPointer, ObReferenceObjectByPointer routine [Kernel-Mode Driver Architecture], P, R, b, c, e, f, i, j, k107_2846f148-4ad5-472a-aa74-4f03c5251aee.xml, kernel.obreferenceobjectbypointer, n, o, r, t, wdm/ObReferenceObjectByPointer, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: TargetRelationNeedsRef, HwStorPortProhibitedDDIs
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
-	ObReferenceObjectByPointer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObReferenceObjectByPointer function


## -description


The <b>ObReferenceObjectByPointer</b> routine increments the pointer reference count for a given object.


## -syntax


````
NTSTATUS ObReferenceObjectByPointer(
  _In_     PVOID           Object,
  _In_     ACCESS_MASK     DesiredAccess,
  _In_opt_ POBJECT_TYPE    ObjectType,
  _In_     KPROCESSOR_MODE AccessMode
);
````


## -parameters




### -param Object [in]

Pointer to the object's body.


### -param DesiredAccess [in]

Specifies a mask representing the requested access to the object.


### -param ObjectType [in, optional]

Pointer to the object type. <i>ObjectType</i> can be <b>*ExEventObjectType</b>, <b>*ExSemaphoreObjectType</b>, <b>*IoFileObjectType</b>, <b>*PsProcessType</b>, <b>*PsThreadType</b>, <b>*SeTokenObjectType</b>, <b>*TmEnlistmentObjectType</b>, <b>*TmResourceManagerObjectType</b>, <b>*TmTransactionManagerObjectType</b>, or <b>*TmTransactionObjectType</b>. 

<div class="alert"><b>Note</b>    The <b>SeTokenObjectType</b> object type is supported in Windows XP and later versions of Windows.</div>
<div> </div>
This parameter can also be <b>NULL</b> if <i>AccessMode</i> is <b>KernelMode</b>.


### -param AccessMode [in]

Indicates the access mode to use for the access check. It must be either <b>UserMode</b> or <b>KernelMode</b>. Lower-level drivers should specify <b>KernelMode</b>.


## -returns



<b>ObReferenceObjectByPointer</b> returns an NTSTATUS value. Possible return values include:




## -remarks



Calling this routine prevents the object from being deleted, possibly by another component's call to <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> or <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. The caller must decrement the reference count with <b>ObDereferenceObject</b> as soon as it is done with the object.




## -see-also

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="..\wdm\nf-wdm-obreferenceobject.md">ObReferenceObject</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObjectByPointer routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

