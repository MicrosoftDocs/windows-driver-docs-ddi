---
UID: NF:ks.KsPinGetNextSiblingPin
title: KsPinGetNextSiblingPin function
author: windows-driver-content
description: The KsPinGetNextSiblingPin function returns the next instantiated pin of the same type and on the same filter as Pin.
old-location: stream\kspingetnextsiblingpin.htm
tech.root: stream
ms.assetid: e6eb5998-50ad-4ad9-8368-4cd29e4f7777
ms.date: 4/23/2018
ms.keywords: KsPinGetNextSiblingPin, KsPinGetNextSiblingPin function [Streaming Media Devices], avfunc_a5363c0a-af05-43a6-aa4d-edd43e076eb7.xml, ks/KsPinGetNextSiblingPin, stream.kspingetnextsiblingpin
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
-	KsPinGetNextSiblingPin
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetNextSiblingPin function


## -description


The<b> KsPinGetNextSiblingPin</b> function returns the next instantiated pin of the same type and on the same filter as <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to find the next instantiated sibling pin.


## -returns



<b>KsPinGetNextSiblingPin</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure representing the next instantiated sibling pin of <i>Pin</i>. If no such pin exists, returns <b>NULL</b>.




## -remarks



<b>KsPinGetNextSiblingPin</b> is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562643">KsGetNextSibling</a>. Note that the object hierarchy is only stable while the appropriate mutex is held, in this case the filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562545">KsFilterGetFirstChildPin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562643">KsGetNextSibling</a>
 

 

