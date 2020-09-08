---
UID: NF:ks.KsFilterAcquireControl
title: KsFilterAcquireControl function (ks.h)
description: The KsFilterAcquireControl function acquires the filter control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilteracquirecontrol.htm
tech.root: stream
ms.assetid: 93dfe9fe-e1af-45db-ab28-fd166f511fcc
ms.date: 04/23/2018
keywords: ["KsFilterAcquireControl function"]
ms.keywords: KsFilterAcquireControl, KsFilterAcquireControl function [Streaming Media Devices], avfunc_63930ae0-491f-4916-a24f-7de5c8fa1ad3.xml, ks/KsFilterAcquireControl, stream.ksfilteracquirecontrol
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
 - KsFilterAcquireControl
 - ks/KsFilterAcquireControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterAcquireControl
---

# KsFilterAcquireControl function


## -description

The<b> KsFilterAcquireControl </b>function acquires the filter control mutex for the AVStream filter specified by <i>Filter</i>.

## -parameters

### -param Filter 

[in]
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> for which to acquire the control mutex.

## -remarks

This function is an inline call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecontrol">KsAcquireControl</a> with the appropriate typecasting. Minidrivers that manipulate the filter control mutex should call this function instead of calling <b>KsAcquireControl </b>directly. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksacquirecontrol">KsAcquireControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterreleasecontrol">KsFilterReleaseControl</a>

