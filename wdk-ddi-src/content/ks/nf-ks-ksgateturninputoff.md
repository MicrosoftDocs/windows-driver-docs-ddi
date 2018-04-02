---
UID: NF:ks.KsGateTurnInputOff
title: KsGateTurnInputOff function
author: windows-driver-content
description: The KsGateTurnInputOff function turns off an existing input to Gate.
old-location: stream\ksgateturninputoff.htm
old-project: stream
ms.assetid: cbcbb49a-8c45-4843-8c21-6c4d8c7bc6c6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateTurnInputOff, KsGateTurnInputOff function [Streaming Media Devices], avfunc_ba116904-80e2-4288-a8d1-d03c0194ef51.xml, ks/KsGateTurnInputOff, stream.ksgateturninputoff
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsGateTurnInputOff
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateTurnInputOff function


## -description


The<b> KsGateTurnInputOff</b> function turns off an existing input to <i>Gate</i>.


## -parameters




### -param Gate [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure that is the gate to transition to the OFF state. Must currently have an input in the ON state. May be an AND gate or an OR gate.


## -returns



None




## -remarks



It is the minidriver's responsibility to verify that the gate that the minidriver passes to <b>KsGateTurnInputOff</b> has at least one ON input. If you call this function with an OR gate that has no inputs currently in the ON state, the call sets the OR gate into an invalid state. If you call this function with an AND gate that has no inputs currently in the ON state, the result is equivalent to adding another input in the OFF state to <i>Gate</i>.

Furthermore, if turning an input off would cause <i>Gate</i> to transition from the open state to the closed state, this call instead turns off an input to whatever gate is attached to <i>Gate</i>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562567">KsGateAddOffInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562568">KsGateAddOffInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562569">KsGateAddOnInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562570">KsGateAddOnInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562578">KsGateRemoveOffInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562580">KsGateRemoveOffInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562584">KsGateRemoveOnInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562585">KsGateRemoveOnInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

