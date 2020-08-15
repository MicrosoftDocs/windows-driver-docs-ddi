---
UID: NF:ks.KsGateTerminateOr
title: KsGateTerminateOr function (ks.h)
description: The KsGateTerminateOr function deletes an existing OR gate and removes an input from any attached AND gate.
old-location: stream\ksgateterminateor.htm
tech.root: stream
ms.assetid: 6d73ce17-1fbc-4d12-87f0-ac10889b85be
ms.date: 04/23/2018
keywords: ["KsGateTerminateOr function"]
ms.keywords: KsGateTerminateOr, KsGateTerminateOr function [Streaming Media Devices], avfunc_b2bf57c5-4f08-456a-bbac-217531cf5bc3.xml, ks/KsGateTerminateOr, stream.ksgateterminateor
f1_keywords:
 - "ks/KsGateTerminateOr"
 - "KsGateTerminateOr"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsGateTerminateOr
targetos: Windows
req.typenames: 
---

# KsGateTerminateOr function


## -description


The<b> KsGateTerminateOr</b> function deletes an existing OR gate and removes an input from any attached AND gate.


## -parameters




### -param OrGate 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure that is the OR gate to delete. This gate must be at the beginning of a gate chain.


## -remarks



Logical gates should be deleted in a front to back manner. <b>KsGateTerminateOr</b> does not update the gate chain for gates that are deleted at the end or in the middle. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeand">KsGateInitializeAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeor">KsGateInitializeOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateterminateand">KsGateTerminateAnd</a>
 

 

