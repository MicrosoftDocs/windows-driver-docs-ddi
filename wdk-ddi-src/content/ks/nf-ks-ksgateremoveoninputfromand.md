---
UID: NF:ks.KsGateRemoveOnInputFromAnd
title: KsGateRemoveOnInputFromAnd function (ks.h)
description: The KsGateRemoveOnInputFromAnd function removes an existing input that is in the ON state from an AND gate.
old-location: stream\ksgateremoveoninputfromand.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsGateRemoveOnInputFromAnd function"]
ms.keywords: KsGateRemoveOnInputFromAnd, KsGateRemoveOnInputFromAnd function [Streaming Media Devices], avfunc_216ba85c-20fe-4160-a76f-53cab6693641.xml, ks/KsGateRemoveOnInputFromAnd, stream.ksgateremoveoninputfromand
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
 - KsGateRemoveOnInputFromAnd
 - ks/KsGateRemoveOnInputFromAnd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateRemoveOnInputFromAnd
---

# KsGateRemoveOnInputFromAnd function


## -description

The<b> KsGateRemoveOnInputFromAnd </b>function removes an existing input that is in the ON state from an AND gate.

## -parameters

### -param AndGate [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the AND gate from which to remove an ON input.

## -remarks

<b>KsGateRemoveOnInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.

For more information, see <a href="/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

This call is an empty function. It should be used for code readability and clarity.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>
