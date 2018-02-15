---
UID: NF:wdm.ObReferenceObject
title: ObReferenceObject macro
author: windows-driver-content
description: The ObReferenceObject routine increments the reference count to the given object.
old-location: kernel\obreferenceobject.htm
old-project: kernel
ms.assetid: d911089a-f23a-4d0e-a333-c01ec3ac89dc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ObReferenceObject routine [Kernel-Mode Driver Architecture], ObReferenceObject, kernel.obreferenceobject, k107_97bb0a8c-e445-484c-959a-03f1c41ab3fe.xml, wdm/ObfReferenceObject, wdm/ObReferenceObject, ObfReferenceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObReferenceObject
-	ObfReferenceObject
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObReferenceObject macro


## -description


The <b>ObReferenceObject</b> routine increments the reference count to the given object. 


## -syntax


````
VOID ObReferenceObject(
  _In_ PVOID Object
);
````


## -parameters




### -param Object [in]

Pointer to the object. The caller obtained this parameter either when it created the object or from a preceding call to <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> after it opened the object. 


## -remarks



<b>ObReferenceObject</b> simply increments the pointer reference count for an object, without making any access checks on the given object, as <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and <a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a> do. 

<b>ObReferenceObject</b> prevents deletion of the object at least until the driver subsequently calls its reciprocal, <b>ObDereferenceObject</b>, or closes the given object. The caller must decrement the reference count with <b>ObDereferenceObject</b> as soon as it is done with the object. 

When the reference count for an object reaches zero, a kernel-mode component can remove the object from the system. However, a driver can remove only those objects that it created, and a driver should never attempt to remove any object that it did not create. 




## -see-also

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObReferenceObject routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

