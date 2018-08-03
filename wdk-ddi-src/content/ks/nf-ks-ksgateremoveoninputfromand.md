---
UID: NF:ks.KsGateRemoveOnInputFromAnd
title: KsGateRemoveOnInputFromAnd function
author: windows-driver-content
description: The KsGateRemoveOnInputFromAnd function removes an existing input that is in the ON state from an AND gate.
old-location: stream\ksgateremoveoninputfromand.htm
tech.root: stream
ms.assetid: ee8bf34e-f7f6-4b1a-8089-2f7a7333c403
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGateRemoveOnInputFromAnd, KsGateRemoveOnInputFromAnd function [Streaming Media Devices], avfunc_216ba85c-20fe-4160-a76f-53cab6693641.xml, ks/KsGateRemoveOnInputFromAnd, stream.ksgateremoveoninputfromand
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
-	KsGateRemoveOnInputFromAnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateRemoveOnInputFromAnd function


## -description


The<b> KsGateRemoveOnInputFromAnd </b>function removes an existing input that is in the ON state from an AND gate.


## -parameters




### -param AndGate [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the AND gate from which to remove an ON input.


## -returns



None




## -remarks



<b>KsGateRemoveOnInputFromAnd</b> should only be used on gates that were specifically created as AND gates; AVStream does not verify that the given gate is truly an AND gate.

For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

This call is an empty function. It should be used for code readability and clarity. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562567">KsGateAddOffInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562569">KsGateAddOnInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562578">KsGateRemoveOffInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

