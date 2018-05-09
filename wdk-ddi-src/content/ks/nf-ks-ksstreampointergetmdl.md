---
UID: NF:ks.KsStreamPointerGetMdl
title: KsStreamPointerGetMdl function
author: windows-driver-content
description: The KsStreamPointerGetMdl function returns the MDL associated with the frame referenced by StreamPointer.
old-location: stream\ksstreampointergetmdl.htm
old-project: stream
ms.assetid: 05d37fbd-9bdc-478a-8772-6f63d1363c1c
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsStreamPointerGetMdl, KsStreamPointerGetMdl function [Streaming Media Devices], avfunc_94dcd1e0-4882-4703-b69a-9ca8b21d30a0.xml, ks/KsStreamPointerGetMdl, stream.ksstreampointergetmdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerGetMdl
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

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure that references the frame for which to return the associated MDL.


## -returns



Returns either a pointer to the <a href="https://msdn.microsoft.com/a1ec4764-4e11-4fb2-b439-ad6b721eb504">memory descriptor list (MDL)</a> describing the frame referenced by <i>StreamPointer</i> or returns <b>NULL</b>. A <b>NULL</b> return value usually indicates that the given stream pointer was not locked at call-time.




## -remarks



The stream pointer <b>must</b> be locked in order for <b>KsStreamPointerGetMdl </b>to execute successfully.

Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567131">KsStreamPointerGetIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892390">KsStreamPointerLock</a>
 

 

