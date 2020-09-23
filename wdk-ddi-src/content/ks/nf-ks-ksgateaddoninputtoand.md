---
UID: NF:ks.KsGateAddOnInputToAnd
title: KsGateAddOnInputToAnd function (ks.h)
description: The KsGateAddOnInputToAnd function adds a new input in the ON state to a given AND gate.
old-location: stream\ksgateaddoninputtoand.htm
tech.root: stream
ms.assetid: cde5e5d8-9af7-452e-afaa-8669c5749c9e
ms.date: 04/23/2018
keywords: ["KsGateAddOnInputToAnd function"]
ms.keywords: KsGateAddOnInputToAnd, KsGateAddOnInputToAnd function [Streaming Media Devices], avfunc_a7d04c8d-b1d7-46a8-bd34-2ec9de4f2196.xml, ks/KsGateAddOnInputToAnd, stream.ksgateaddoninputtoand
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
 - KsGateAddOnInputToAnd
 - ks/KsGateAddOnInputToAnd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateAddOnInputToAnd
---

# KsGateAddOnInputToAnd function


## -description

The<b> KsGateAddOnInputToAnd</b> function adds a new input in the ON state to a given AND gate.

## -parameters

### -param AndGate 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the AND gate to which to add a new ON input.

## -remarks

This function should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

This call is an empty function. It should be used for code readability and clarity.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>