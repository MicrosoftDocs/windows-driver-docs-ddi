---
UID: NF:wdm.ObfReferenceObject
title: ObfReferenceObject function
description: The ObReferenceObject routine increments the reference count to the given object.
old-location: kernel\obreferenceobject.htm
tech.root: kernel
ms.assetid: d911089a-f23a-4d0e-a333-c01ec3ac89dc
ms.date: 04/30/2018
ms.keywords: ObReferenceObject, ObReferenceObject routine [Kernel-Mode Driver Architecture], ObfReferenceObject, k107_97bb0a8c-e445-484c-959a-03f1c41ab3fe.xml, kernel.obreferenceobject, wdm/ObReferenceObject, wdm/ObfReferenceObject
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ObReferenceObject
-	ObfReferenceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# ObfReferenceObject function


## -description


The <b>ObReferenceObject</b> routine increments the reference count to the given object. 


## -parameters




### -param Object [in]

Pointer to the object. The caller obtained this parameter either when it created the object or from a preceding call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> after it opened the object. 


## -returns



<b>ObReferenceObject</b> returns a value that is reserved for system use. Drivers must treat this value as VOID. 




## -remarks



<b>ObReferenceObject</b> simply increments the pointer reference count for an object, without making any access checks on the given object, as <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff558686">ObReferenceObjectByPointer</a> do. 

<b>ObReferenceObject</b> prevents deletion of the object at least until the driver subsequently calls its reciprocal, <b>ObDereferenceObject</b>, or closes the given object. The caller must decrement the reference count with <b>ObDereferenceObject</b> as soon as it is done with the object. 

When the reference count for an object reaches zero, a kernel-mode component can remove the object from the system. However, a driver can remove only those objects that it created, and a driver should never attempt to remove any object that it did not create. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558686">ObReferenceObjectByPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
 

 

