---
UID: NF:ks.KSMETHOD_SET_IRP_STORAGE
title: KSMETHOD_SET_IRP_STORAGE macro
author: windows-driver-content
description: This macro returns a pointer to the KSMETHOD_SET in which the method is located.
old-location: stream\ksmethod_set_irp_storage.htm
old-project: stream
ms.assetid: bc0a309d-305e-400a-b571-7958926dd1dc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSMETHOD_SET_IRP_STORAGE, KSMETHOD_SET_IRP_STORAGE macro [Streaming Media Devices], ks/KSMETHOD_SET_IRP_STORAGE, ksfunc_d413bf2a-7d63-48c2-9e75-d84cf1344f5c.xml, stream.ksmethod_set_irp_storage
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	KSMETHOD_SET_IRP_STORAGE
product: Windows
targetos: Windows
req.typenames: 
---

# KSMETHOD_SET_IRP_STORAGE macro


## -description


This macro returns a pointer to the <a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a> in which the method is located.


## -syntax


````
VOID KSMETHOD_SET_IRP_STORAGE(
  [in] IRP Irp
);
````


## -parameters




### -param Irp [in]

Specifies the IRP passed to the handler routine.


## -remarks



The pointer to a KSMETHOD_SET structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a> and <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:

<pre class="syntax" xml:space="preserve"><code>#define KSMETHOD_SET_IRP_STORAGE(Irp)       (*(const KSMETHOD_SET**)&amp;(Irp)-&gt;Tail.Overlay.DriverContext[0])</code></pre>



## -see-also

<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\nf-ks-ksfastmethodhandler.md">KsFastMethodHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>



<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



 

 


