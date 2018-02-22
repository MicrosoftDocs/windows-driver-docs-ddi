---
UID: NF:wdm.ObDereferenceObject
title: ObDereferenceObject macro
author: windows-driver-content
description: The ObDereferenceObject routine decrements the given object's reference count and performs retention checks.
old-location: kernel\obdereferenceobject.htm
old-project: kernel
ms.assetid: 8cd2d7ae-ebbe-41c6-8773-7a517bc6f714
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ObDereferenceObject routine [Kernel-Mode Driver Architecture], ObDereferenceObject, wdm/ObDereferenceObject, k107_bc67abd9-66b2-4cd7-81c0-48ad0fa6c87d.xml, kernel.obdereferenceobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	ObDereferenceObject
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObDereferenceObject macro


## -description


The <b>ObDereferenceObject</b> routine decrements the given object's reference count and performs retention checks.


## -syntax


````
VOID ObDereferenceObject(
  _In_ PVOID Object
);
````


## -parameters




### -param a

TBD






#### - Object [in]

Pointer to the object's body. 


## -remarks



<b>ObDereferenceObject</b> decreases the reference count of an object by one. If the object was created as temporary (the OBJ_PERMANENT flag was not specified on creation), and the reference count reaches zero, the object can be deleted by the system.

A driver can delete a temporary object it created by decreasing its reference count to zero. A driver must never attempt to delete an object it did not create.

An object is permanent if it was created with the OBJ_PERMANENT object attribute flag specified. (For more information about object attributes, see <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>.) A permanent object is created with a reference count of one, so it is not deleted when the driver dereferences it. A driver can only delete a permanent object it created by using the <a href="..\wdm\nf-wdm-zwmaketemporaryobject.md">ZwMakeTemporaryObject</a> routine to make it temporary. Use the following steps to delete a permanent object that you created:

<ol>
<li>
Call <b>ObDereferenceObject</b>.

</li>
<li>
Call the appropriate <b>ZwOpen<i>Xxx</i></b> or <b>ZwCreate<i>Xxx</i></b> routine to get a handle for the object, if necessary.

</li>
<li>
Call <a href="..\wdm\nf-wdm-zwmaketemporaryobject.md">ZwMakeTemporaryObject</a> with the handle obtained in step 2.

</li>
<li>
Call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> with the handle obtained in step 2.

</li>
</ol>
<div class="alert"><b>Important</b>  
     Use <a href="..\wdm\nf-wdm-obdereferenceobjectdeferdelete.md">ObDereferenceObjectDeferDelete</a> instead of <b>ObDereferenceObject</b> for any object, particularly <a href="https://msdn.microsoft.com/43bf96ed-8be8-4670-a310-99cd7c7f9073">Kernel Transaction Manager</a> (KTM) objects, when the immediate deletion by the current thread of the object (by using <b>ObDereferenceObject</b>) might result in a deadlock.</div>
<div> </div>



## -see-also

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-zwmaketemporaryobject.md">ZwMakeTemporaryObject</a>



<a href="..\wdm\nf-wdm-obdereferenceobjectdeferdelete.md">ObDereferenceObjectDeferDelete</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObDereferenceObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

