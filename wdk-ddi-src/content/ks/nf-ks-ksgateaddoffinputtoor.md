---
UID: NF:ks.KsGateAddOffInputToOr
title: KsGateAddOffInputToOr function
author: windows-driver-content
description: The KsGateAddOffInputToOr function adds a new input in the OFF state to a given OR gate.
old-location: stream\ksgateaddoffinputtoor.htm
old-project: stream
ms.assetid: 93d5076c-d8db-4b4b-b390-5f9072d2ae63
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateAddOffInputToOr, KsGateAddOffInputToOr function [Streaming Media Devices], avfunc_abee7d7c-388b-4a48-a573-6b46a1c9dc46.xml, ks/KsGateAddOffInputToOr, stream.ksgateaddoffinputtoor
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
-	KsGateAddOffInputToOr
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateAddOffInputToOr function


## -description


The<b> KsGateAddOffInputToOr</b> function adds a new input in the OFF state to a given OR gate. 


## -parameters




### -param OrGate [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the OR gate to which to add a new OFF input.


## -returns



None




## -remarks



This function should only be used on gates that were specifically created as OR gates; AVStream does not verify that the given gate is an OR gate.

This call is an empty function. It should be used for code readability and clarity. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562570">KsGateAddOnInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562580">KsGateRemoveOffInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562585">KsGateRemoveOnInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

