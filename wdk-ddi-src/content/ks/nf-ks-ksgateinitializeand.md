---
UID: NF:ks.KsGateInitializeAnd
title: KsGateInitializeAnd function (ks.h)
description: The KsGateInitializeAnd function initializes a KSGATE structure as an AND gate and attaches it to the OR gate specified by NextOrGate.
old-location: stream\ksgateinitializeand.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGateInitializeAnd function"]
ms.keywords: KsGateInitializeAnd, KsGateInitializeAnd function [Streaming Media Devices], avfunc_9eb102c9-08f4-44f7-bc3e-889aa8f85f23.xml, ks/KsGateInitializeAnd, stream.ksgateinitializeand
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGateInitializeAnd
 - ks/KsGateInitializeAnd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateInitializeAnd
---

# KsGateInitializeAnd function


## -description

The<b> KsGateInitializeAnd</b> function initializes a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure as an AND gate and attaches it to the OR gate specified by <i>NextOrGate</i>.

## -parameters

### -param AndGate 

[in]
A pointer to the KSGATE structure to initialize as a new AND gate.

### -param NextOrGate 

[in, optional]
A pointer to an existing KSGATE structure to which <i>AndGate</i> attaches. This parameter should be an OR gate and is optional.

## -remarks

The next gate (following <i>AndGate</i>) must be an OR gate, whether it is specified in this call or later. For more information, see <a href="/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

<b>KsGateInitializeAnd</b> is an inline call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitialize">KsGateInitialize</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitialize">KsGateInitialize</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeor">KsGateInitializeOr</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateterminateand">KsGateTerminateAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateterminateor">KsGateTerminateOr</a>
