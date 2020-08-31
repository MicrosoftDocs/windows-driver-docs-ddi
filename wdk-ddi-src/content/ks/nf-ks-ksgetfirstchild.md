---
UID: NF:ks.KsGetFirstChild
title: KsGetFirstChild function (ks.h)
description: The KsGetFirstChild function returns the first AVStream child object of Object.
old-location: stream\ksgetfirstchild.htm
tech.root: stream
ms.assetid: f7ff16ac-fe20-4998-a8b3-d1d02c418938
ms.date: 04/23/2018
keywords: ["KsGetFirstChild function"]
ms.keywords: KsGetFirstChild, KsGetFirstChild function [Streaming Media Devices], avfunc_cfdde7e3-bc8b-46df-abf4-fe43ac9b0bfc.xml, ks/KsGetFirstChild, stream.ksgetfirstchild
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
 - KsGetFirstChild
 - ks/KsGetFirstChild
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetFirstChild
---

# KsGetFirstChild function


## -description

The<b> KsGetFirstChild</b> function returns the first AVStream child object of <i>Object</i>.

## -parameters

### -param Object 

[in]
The object for which to find the first AVStream child object.

## -returns

<b>KsGetFirstChild</b> returns the first AVStream child object of <i>Object</i>. If no such child object exists, it returns <b>NULL</b>.

## -remarks

To see the hierarchical organization of AVStream objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-object-hierarchy">AVStream Object Hierarchy</a>.

Minidrivers rarely call this function directly. Those that do must manually perform typecasts to and from PVOID. There are a number of functions that are inline calls to <b>KsGetFirstChild</b> and perform typecasts for you: <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdevicegetfirstchildfilterfactory">KsDeviceGetFirstChildFilterFactory</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetfirstchildfilter">KsFilterFactoryGetFirstChildFilter</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdevicegetfirstchildfilterfactory">KsDeviceGetFirstChildFilterFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetfirstchildfilter">KsFilterFactoryGetFirstChildFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetfirstchildpin">KsFilterGetFirstChildPin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetparent">KsGetParent</a>

