---
UID: NF:ks.KSMETHOD_ITEM_IRP_STORAGE
title: KSMETHOD_ITEM_IRP_STORAGE macro
description: This macro accesses a pointer to the relevant KSMETHOD_ITEM. Note that this pointer is only set when using KsMethodHandlerWithAllocator.
old-location: stream\ksmethod_item_irp_storage.htm
tech.root: stream
ms.assetid: 8c06da38-6f3b-4cd6-8331-c88758a7f00b
ms.date: 04/23/2018
ms.keywords: KSMETHOD_ITEM_IRP_STORAGE, KSMETHOD_ITEM_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_ITEM_IRP_STORAGE, ksfunc_f9a51af4-aa4e-432d-99e3-03052e99b902.xml, stream.ksmethod_item_irp_storage
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSMETHOD_ITEM_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSMETHOD_ITEM_IRP_STORAGE macro


## -description


This macro accesses a pointer to the relevant <a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>. Note that this pointer is only set when using <a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>.


## -parameters




### -param Irp [in]

Specifies the IRP passed to the handler routine.


## -remarks



The pointer to a KSMETHOD_ITEM structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_ITEM_IRP_STORAGE(Irp)      (*(const KSMETHOD_ITEM**)&amp;(Irp)-&gt;Tail.Overlay.DriverContext[3])</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563423">KSMETHOD_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561940">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>
 

 

