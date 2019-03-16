---
UID: NF:ks.KsGateAddOnInputToOr
title: KsGateAddOnInputToOr function (ks.h)
description: The KsGateAddOnInputToOr function adds a new input in the ON state to a given OR gate.
old-location: stream\ksgateaddoninputtoor.htm
tech.root: stream
ms.assetid: aaa6891b-f9f9-40d5-b0eb-e17f511e2611
ms.date: 04/23/2018
ms.keywords: KsGateAddOnInputToOr, KsGateAddOnInputToOr function [Streaming Media Devices], avfunc_f19411cd-eca5-4acb-b0ca-f470a72a4afd.xml, ks/KsGateAddOnInputToOr, stream.ksgateaddoninputtoor
ms.topic: function
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
- KsGateAddOnInputToOr
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateAddOnInputToOr function


## -description


The<b> KsGateAddOnInputToOr</b> function adds a new input in the ON state to a given OR gate.


## -parameters




### -param OrGate [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the OR gate to which to add a new ON input.


## -returns



None




## -remarks



Adding an ON input to an OR gate in the OFF or closed state results in the gate opening and the transition being propagated to any gates attached to <i>OrGate</i>. Use this function only with gates that were specifically created as OR gates. AVStream does not verify that the given gate is an OR gate.

This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>. Minidrivers should call <b>KsGateAddOnInputToOr</b> rather than <b>KsGateTurnInputOn</b> if conceptually adding a new input to the gate. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562568">KsGateAddOffInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562580">KsGateRemoveOffInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562585">KsGateRemoveOnInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

