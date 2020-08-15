---
UID: NF:ks.KsGateRemoveOffInputFromAnd
title: KsGateRemoveOffInputFromAnd function (ks.h)
description: The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate.
old-location: stream\ksgateremoveoffinputfromand.htm
tech.root: stream
ms.assetid: 37f463bb-6b7a-4262-9e4b-3650025acb7c
ms.date: 04/23/2018
keywords: ["KsGateRemoveOffInputFromAnd function"]
ms.keywords: KsGateRemoveOffInputFromAnd, KsGateRemoveOffInputFromAnd function [Streaming Media Devices], avfunc_604705b6-08f8-4048-8b29-f89b645f971a.xml, ks/KsGateRemoveOffInputFromAnd, stream.ksgateremoveoffinputfromand
f1_keywords:
 - "ks/KsGateRemoveOffInputFromAnd"
 - "KsGateRemoveOffInputFromAnd"
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
- KsGateRemoveOffInputFromAnd
targetos: Windows
req.typenames: 
---

# KsGateRemoveOffInputFromAnd function


## -description


The<b> KsGateRemoveOffInputFromAnd</b> function removes an existing input that is in the OFF state from an AND gate.


## -parameters




### -param AndGate 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the AND gate from which to remove an OFF input.


## -remarks



Removing the last OFF input from the gate results in the gate opening and the transition being propagated to any gates connected to <i>AndGate</i>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOffInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

<b>KsGateRemoveOffInputFromAnd</b> is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>. If conceptually removing an existing input to the gate rather than turning it off, a minidriver should call <b>KsGateRemoveOffInputFromAnd</b> instead of <b>KsGateTurnInputOn</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>
 

 

