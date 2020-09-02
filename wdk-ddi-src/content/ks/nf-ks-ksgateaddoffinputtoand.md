---
UID: NF:ks.KsGateAddOffInputToAnd
title: KsGateAddOffInputToAnd function (ks.h)
description: The KsGateAddOffInputToAnd function adds a new input in the OFF state to a given AND gate.
old-location: stream\ksgateaddoffinputtoand.htm
tech.root: stream
ms.assetid: 53e03b1d-0995-43cf-945a-22834a9e8240
ms.date: 04/23/2018
keywords: ["KsGateAddOffInputToAnd function"]
ms.keywords: KsGateAddOffInputToAnd, KsGateAddOffInputToAnd function [Streaming Media Devices], avfunc_52efe27b-d77a-490d-beba-3a05b3d5ed83.xml, ks/KsGateAddOffInputToAnd, stream.ksgateaddoffinputtoand
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
 - KsGateAddOffInputToAnd
 - ks/KsGateAddOffInputToAnd
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGateAddOffInputToAnd
---

# KsGateAddOffInputToAnd function


## -description

The<b> KsGateAddOffInputToAnd</b> function adds a new input in the OFF state to a given AND gate.

## -parameters

### -param AndGate 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the AND gate to which to add a new OFF input.

## -remarks

Adding an OFF input to an open AND gate closes the gate and propagates the close down to any attached gates.

This function should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateAddOffInputToAnd</b> is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>. If conceptually adding a new input to a gate, the minidriver should call <b>KsGateAddOffInputToAnd</b> rather than <b>KsGateTurnInputOff</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>

