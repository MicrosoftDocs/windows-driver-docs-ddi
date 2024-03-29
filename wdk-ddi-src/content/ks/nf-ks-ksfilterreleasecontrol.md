---
UID: NF:ks.KsFilterReleaseControl
title: KsFilterReleaseControl function (ks.h)
description: The KsFilterReleaseControl function releases the control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilterreleasecontrol.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsFilterReleaseControl function"]
ms.keywords: KsFilterReleaseControl, KsFilterReleaseControl function [Streaming Media Devices], avfunc_ca99338c-1cae-4ef4-8ef5-76ee368ae1d6.xml, ks/KsFilterReleaseControl, stream.ksfilterreleasecontrol
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
 - KsFilterReleaseControl
 - ks/KsFilterReleaseControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsFilterReleaseControl
---

# KsFilterReleaseControl function


## -description

The<b> KsFilterReleaseControl </b>function releases the control mutex for the AVStream filter specified by <i>Filter</i>.

## -parameters

### -param Filter [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the AVStream filter for which to release the control mutex.

## -remarks

This function is an inline call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksreleasecontrol">KsReleaseControl</a> with the appropriate typecasting. When manipulating a filter, minidrivers should call this function instead of calling <b>KsReleaseControl</b> directly.

For a description of the filter control mutex, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfilteracquirecontrol">KsFilterAcquireControl</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksreleasecontrol">KsReleaseControl</a>
