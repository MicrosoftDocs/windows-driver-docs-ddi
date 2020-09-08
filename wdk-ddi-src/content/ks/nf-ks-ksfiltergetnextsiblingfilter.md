---
UID: NF:ks.KsFilterGetNextSiblingFilter
title: KsFilterGetNextSiblingFilter function (ks.h)
description: The KsFilterGetNextSiblingFilter function returns the next instantiated filter belonging to the parent filter factory of Filter.
old-location: stream\ksfiltergetnextsiblingfilter.htm
tech.root: stream
ms.assetid: 0b0a306a-6066-4a7d-ae2d-12eb8bb3adc0
ms.date: 04/23/2018
keywords: ["KsFilterGetNextSiblingFilter function"]
ms.keywords: KsFilterGetNextSiblingFilter, KsFilterGetNextSiblingFilter function [Streaming Media Devices], avfunc_bda9f36a-10d4-4de3-88b2-a358aad4fd04.xml, ks/KsFilterGetNextSiblingFilter, stream.ksfiltergetnextsiblingfilter
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterGetNextSiblingFilter
 - ks/KsFilterGetNextSiblingFilter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterGetNextSiblingFilter
---

# KsFilterGetNextSiblingFilter function


## -description

The<b> KsFilterGetNextSiblingFilter</b> function returns the next instantiated filter belonging to the parent filter factory of <i>Filter</i>.

## -parameters

### -param Filter 

[in]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure for which to find the next sibling filter.

## -returns

<b>KsFilterGetNextSiblingFilter</b> returns a pointer to the next sibling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure of <i>Filter</i>. If no such instantiated filter exists, it returns <b>NULL</b>.

## -remarks

This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetnextsibling">KsGetNextSibling</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetfirstchildfilter">KsFilterFactoryGetFirstChildFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetnextsibling">KsGetNextSibling</a>

