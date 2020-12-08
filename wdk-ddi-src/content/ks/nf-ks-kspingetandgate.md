---
UID: NF:ks.KsPinGetAndGate
title: KsPinGetAndGate function (ks.h)
description: The KsPinGetAndGate function returns the processing control gate for Pin.
old-location: stream\kspingetandgate.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsPinGetAndGate function"]
ms.keywords: KsPinGetAndGate, KsPinGetAndGate function [Streaming Media Devices], avfunc_a4159ef9-1a69-4716-96ce-4fabd1ee6218.xml, ks/KsPinGetAndGate, stream.kspingetandgate
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinGetAndGate
 - ks/KsPinGetAndGate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinGetAndGate
---

# KsPinGetAndGate function


## -description

The<b> KsPinGetAndGate</b> function returns the processing control gate for <i>Pin</i>.

## -parameters

### -param Pin 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> for which to return the processing control gate.

## -returns

Returns a pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> representing the processing control gate for <i>Pin</i>.

## -remarks

For more information, see <a href="/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetandgate">KsFilterGetAndGate</a>
