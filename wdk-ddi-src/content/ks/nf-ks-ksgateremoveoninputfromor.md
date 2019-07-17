---
UID: NF:ks.KsGateRemoveOnInputFromOr
title: KsGateRemoveOnInputFromOr function (ks.h)
description: The KsGateRemoveOnInputFromOr function removes an existing input that is in the ON state from an OR gate.
old-location: stream\ksgateremoveoninputfromor.htm
tech.root: stream
ms.assetid: e7226684-afbf-46e1-aeb2-6b0c60c12680
ms.date: 04/23/2018
ms.keywords: KsGateRemoveOnInputFromOr, KsGateRemoveOnInputFromOr function [Streaming Media Devices], avfunc_6f131d80-de01-44e6-a17d-eb7f9b0b968f.xml, ks/KsGateRemoveOnInputFromOr, stream.ksgateremoveoninputfromor
ms.topic: function
f1_keywords:
 - "ks/KsGateRemoveOnInputFromOr"
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
- KsGateRemoveOnInputFromOr
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateRemoveOnInputFromOr function


## -description


The<b> KsGateRemoveOnInputFromOr </b>function removes an existing input that is in the ON state from an OR gate.


## -parameters




### -param OrGate [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksgate">KSGATE</a> structure representing the OR gate from which to remove an ON input.


## -returns



None




## -remarks



Removing the last ON input from a given OR gate results in the gate closing and the transition being propagated to any gates connected to <i>OrGate</i>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

<b>KsGateRemoveOnInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is an AND gate.

This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>. If conceptually removing an existing input to a gate, a minidriver should call <b>KsGateRemoveOnInputFromOr</b> rather than <b>KsGateTurnInputOff</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateaddoffinputtoor">KsGateAddOffInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateaddoninputtoor">KsGateAddOnInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateremoveoffinputfromor">KsGateRemoveOffInputFromOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>
 

 

