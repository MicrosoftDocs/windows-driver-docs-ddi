---
UID: NF:ks.KsGetNextSibling
title: KsGetNextSibling function (ks.h)
description: The KsGetNextSibling function returns the next sibling of a given object.
old-location: stream\ksgetnextsibling.htm
tech.root: stream
ms.assetid: 509cf778-2b0c-4dd2-982d-0c7be95ad407
ms.date: 04/23/2018
keywords: ["KsGetNextSibling function"]
ms.keywords: KsGetNextSibling, KsGetNextSibling function [Streaming Media Devices], avfunc_0fedfc95-34c0-44d9-bed4-fff6bf6bd467.xml, ks/KsGetNextSibling, stream.ksgetnextsibling
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetNextSibling
 - ks/KsGetNextSibling
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetNextSibling
---

# KsGetNextSibling function


## -description

The<b> KsGetNextSibling </b>function returns the next sibling of a given object.

## -parameters

### -param Object 

[in]
The object for which to find the next sibling.

## -returns

<b>KsGetNextSibling</b> returns the next sibling object of <i>Object</i>. If no such sibling object exists, it returns <b>NULL</b>.

## -remarks

If <i>Object</i> is a filter factory, <b>KsGetNextSibling </b>returns the next filter factory belonging to the parent device, and so on. Callers must perform appropriate typecasting to and from PVOID.

The object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

Minidrivers rarely call <b>KsGetNextSibling</b> directly. There are a number of functions that are inline calls to <b>KsGetNextSibling</b> and that perform the typecasting for you: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetnextsiblingfilterfactory">KsFilterFactoryGetNextSiblingFilterFactory</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetnextsiblingfilter">KsFilterGetNextSiblingFilter</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilterfactory">KSFILTERFACTORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetnextsiblingfilterfactory">KsFilterFactoryGetNextSiblingFilterFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetnextsiblingfilter">KsFilterGetNextSiblingFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>

