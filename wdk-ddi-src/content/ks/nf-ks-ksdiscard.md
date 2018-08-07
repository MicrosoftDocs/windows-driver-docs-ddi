---
UID: NF:ks.KsDiscard
title: KsDiscard macro
author: windows-driver-content
description: The KsDiscard macro removes a given item from an object bag.
old-location: stream\ksdiscard.htm
tech.root: stream
ms.assetid: cbd1cd9b-c3bd-4827-88e6-4b80d6ba7320
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsDiscard, KsDiscard function [Streaming Media Devices], avfunc_645e5574-6c6b-4336-87fe-fe777f7d1c91.xml, ks/KsDiscard, stream.ksdiscard
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDiscard
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDiscard macro


## -description


The<b> KsDiscard </b>macro removes a given item from an object bag.


## -parameters




### -param Object [in]

The item pointed to by <i>Pointer</i> is removed from the object bag associated with this object. Can be of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>.


### -param Pointer [in]

A pointer to the item to be removed from the requested object's bag.


## -remarks



This function is implemented as a C-style preprocessing macro in the <i>Ks.h</i> header.

<b>KsDiscard</b> calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566798">KsRemoveItemFromObjectBag</a>, passing the object bag associated with <i>Object</i> (<i>Object -&gt; Bag</i>), the item specified by <i>Pointer</i>, and <b>TRUE</b> for the <i>Free</i> parameter. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566798">KsRemoveItemFromObjectBag</a>
 

 

