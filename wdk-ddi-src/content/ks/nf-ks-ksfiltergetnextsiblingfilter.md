---
UID: NF:ks.KsFilterGetNextSiblingFilter
title: KsFilterGetNextSiblingFilter function
author: windows-driver-content
description: The KsFilterGetNextSiblingFilter function returns the next instantiated filter belonging to the parent filter factory of Filter.
old-location: stream\ksfiltergetnextsiblingfilter.htm
old-project: stream
ms.assetid: 0b0a306a-6066-4a7d-ae2d-12eb8bb3adc0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterGetNextSiblingFilter, KsFilterGetNextSiblingFilter function [Streaming Media Devices], avfunc_bda9f36a-10d4-4de3-88b2-a358aad4fd04.xml, ks/KsFilterGetNextSiblingFilter, stream.ksfiltergetnextsiblingfilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsFilterGetNextSiblingFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetNextSiblingFilter function


## -description


The<b> KsFilterGetNextSiblingFilter</b> function returns the next instantiated filter belonging to the parent filter factory of <i>Filter</i>.


## -parameters




### -param Filter [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure for which to find the next sibling filter.


## -returns



<b>KsFilterGetNextSiblingFilter</b> returns a pointer to the next sibling <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure of <i>Filter</i>. If no such instantiated filter exists, it returns <b>NULL</b>.




## -remarks



This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562643">KsGetNextSibling</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562643">KsGetNextSibling</a>
 

 

