---
UID: NF:ks.KsPinGetFirstCloneStreamPointer
title: KsPinGetFirstCloneStreamPointer function
author: windows-driver-content
description: The KsPinGetFirstCloneStreamPointer function returns the first cloned stream pointer on Pin.
old-location: stream\kspingetfirstclonestreampointer.htm
old-project: stream
ms.assetid: 9b4880af-d748-4a4e-92ec-8081138d4e27
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinGetFirstCloneStreamPointer, KsPinGetFirstCloneStreamPointer function [Streaming Media Devices], avfunc_2a3d17ef-c1b8-4b22-af1e-7f9bb01c1183.xml, ks/KsPinGetFirstCloneStreamPointer, stream.kspingetfirstclonestreampointer
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
-	KsPinGetFirstCloneStreamPointer
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetFirstCloneStreamPointer function


## -description


The<b> KsPinGetFirstCloneStreamPointer</b> function returns the first cloned stream pointer on <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure on which to return the first clone stream pointer.


## -returns



<b>KsPinGetFirstCloneStreamPointer</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a> structure. This pointer points to the first cloned stream pointer on <i>Pin</i>. If no clone stream pointers exist for <i>Pin</i>, <b>KsPinGetFirstCloneStreamPointer</b> returns <b>NULL</b>.




## -remarks



<b>KsPinGetFirstCloneStreamPointer</b>, along with <a href="https://msdn.microsoft.com/library/windows/hardware/ff567133">KsStreamPointerGetNextClone</a> can be used to enumerate all clone stream pointers on a given pin in the order in which they were cloned. Also see <a href="https://msdn.microsoft.com/4bac68a0-34d2-431a-9ed9-8a42751a736f">Stream Pointers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567139">KSSTREAM_POINTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn892389">KsStreamPointerClone</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567133">KsStreamPointerGetNextClone</a>
 

 

