---
UID: NF:ks.KsStreamPointerGetMdl
title: KsStreamPointerGetMdl function (ks.h)
description: The KsStreamPointerGetMdl function returns the MDL associated with the frame referenced by StreamPointer.
old-location: stream\ksstreampointergetmdl.htm
tech.root: stream
ms.assetid: 05d37fbd-9bdc-478a-8772-6f63d1363c1c
ms.date: 04/23/2018
ms.keywords: KsStreamPointerGetMdl, KsStreamPointerGetMdl function [Streaming Media Devices], avfunc_94dcd1e0-4882-4703-b69a-9ca8b21d30a0.xml, ks/KsStreamPointerGetMdl, stream.ksstreampointergetmdl
ms.topic: function
f1_keywords:
 - "ks/KsStreamPointerGetMdl"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsStreamPointerGetMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamPointerGetMdl function


## -description


The<b> KsStreamPointerGetMdl </b>function returns the MDL associated with the frame referenced by <i>StreamPointer</i>.


## -parameters




### -param StreamPointer [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksstream_pointer">KSSTREAM_POINTER</a> structure that references the frame for which to return the associated MDL.


## -returns



Returns either a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/">memory descriptor list (MDL)</a> describing the frame referenced by <i>StreamPointer</i> or returns <b>NULL</b>. A <b>NULL</b> return value usually indicates that the given stream pointer was not locked at call-time.




## -remarks



The stream pointer <b>must</b> be locked in order for <b>KsStreamPointerGetMdl </b>to execute successfully.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-pointers">Stream Pointers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksstreampointergetirp">KsStreamPointerGetIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ks-ksstreampointerlock">KsStreamPointerLock</a>
 

 

