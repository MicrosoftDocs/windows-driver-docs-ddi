---
UID: NF:ks.KsGateRemoveOffInputFromOr
title: KsGateRemoveOffInputFromOr function (ks.h)
description: The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate.
old-location: stream\ksgateremoveoffinputfromor.htm
tech.root: stream
ms.assetid: 191874ec-5d08-430e-ad14-520392e1a904
ms.date: 04/23/2018
ms.keywords: KsGateRemoveOffInputFromOr, KsGateRemoveOffInputFromOr function [Streaming Media Devices], avfunc_6431bb18-7f16-4a0f-b012-c0137d85fba8.xml, ks/KsGateRemoveOffInputFromOr, stream.ksgateremoveoffinputfromor
ms.topic: function
f1_keywords:
 - "ks/KsGateRemoveOffInputFromOr"
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
- KsGateRemoveOffInputFromOr
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateRemoveOffInputFromOr function


## -description


The<b> KsGateRemoveOffInputFromOr</b> function removes an existing input that is in the OFF state from an OR gate.


## -parameters




### -param OrGate [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure representing the OR gate from which to remove an OFF input.


## -remarks



<b>KsGateRemoveOffInputFromOr</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

This call is an empty function. It should be used for code readability and clarity. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoffinputtoor">KsGateAddOffInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateaddoninputtoor">KsGateAddOnInputToOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateremoveoninputfromor">KsGateRemoveOnInputFromOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputoff">KsGateTurnInputOff</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateturninputon">KsGateTurnInputOn</a>
 

 

