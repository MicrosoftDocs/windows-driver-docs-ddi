---
UID: NF:ks.KSMETHOD_TYPE_IRP_STORAGE
title: KSMETHOD_TYPE_IRP_STORAGE macro
author: windows-driver-content
description: This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact.
old-location: stream\ksmethod_type_irp_storage.htm
tech.root: stream
ms.assetid: f5327cbf-e71b-4c1c-94c0-0e27afb4d7cf
ms.date: 4/23/2018
ms.keywords: KSMETHOD_TYPE_IRP_STORAGE, KSMETHOD_TYPE_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_TYPE_IRP_STORAGE, ksfunc_de99d882-5298-4972-9d16-fa4478d6229c.xml, stream.ksmethod_type_irp_storage
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
-	KSMETHOD_TYPE_IRP_STORAGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# KSMETHOD_TYPE_IRP_STORAGE macro


## -description


This macro accesses the type of method as described in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>. If the method will be processed asynchronously using <a href="https://msdn.microsoft.com/library/windows/hardware/ff561715">KsDispatchSpecificMethod</a>, this storage must be maintained intact.


## -parameters




### -param Irp [in]

Specifies the IRP passed to the handler routine.


## -remarks



The relevant KSMETHOD_ITEM structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_TYPE_IRP_STORAGE(Irp)      (*(ULONG_PTR*)(&amp;(Irp)-&gt;Tail.Overlay.DriverContext[2]))</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563423">KSMETHOD_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561940">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563401">KsMethodHandlerWithAllocator</a>
 

 

