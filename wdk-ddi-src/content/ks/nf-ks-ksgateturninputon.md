---
UID: NF:ks.KsGateTurnInputOn
title: KsGateTurnInputOn function (ks.h)
description: The KsGateTurnInputOn function turns on an existing input to Gate.
old-location: stream\ksgateturninputon.htm
tech.root: stream
ms.assetid: 68c914bf-a293-42b0-85aa-c9e8f2ba18ac
ms.date: 04/23/2018
ms.keywords: KsGateTurnInputOn, KsGateTurnInputOn function [Streaming Media Devices], avfunc_9aaa9c85-b3a1-49ae-8135-6402f7bc1755.xml, ks/KsGateTurnInputOn, stream.ksgateturninputon
ms.topic: function
f1_keywords:
 - "ks/KsGateTurnInputOn"
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
- KsGateTurnInputOn
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateTurnInputOn function


## -description


The<b> KsGateTurnInputOn</b> function turns on an existing input to <i>Gate</i>.


## -parameters




### -param Gate [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the gate that currently has an input in the OFF state to transition to the ON state. May be an AND gate or an OR gate.


## -returns



None




## -remarks



It is the minidriver's responsibility to verify that the gate that the minidriver passes to <b>KsGateTurnInputOn</b> has at least one OFF input. If you call this function with an AND gate that has no inputs currently in the OFF state, the call sets the AND gate into an invalid state. If you call this function with an OR gate that has no inputs currently in the OFF state, the result is equivalent to adding another input in the ON state to <i>Gate</i>.

Furthermore, if turning an input on would cause <i>Gate</i> to transition from the closed state to the open state, this call instead turns on an input to whatever gate is attached to <i>Gate</i>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoand">KsGateAddOffInputToAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoor">KsGateAddOffInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoand">KsGateAddOnInputToAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoor">KsGateAddOnInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromand">KsGateRemoveOffInputFromAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoffinputfromor">KsGateRemoveOffInputFromOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromand">KsGateRemoveOnInputFromAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromor">KsGateRemoveOnInputFromOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>
 

 

