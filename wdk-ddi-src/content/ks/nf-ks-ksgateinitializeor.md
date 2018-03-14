---
UID: NF:ks.KsGateInitializeOr
title: KsGateInitializeOr function
author: windows-driver-content
description: The KsGateInitializeOr function initializes a KSGATE structure as an OR gate and attaches it to the AND gate specified by NextAndGate.
old-location: stream\ksgateinitializeor.htm
old-project: stream
ms.assetid: a02a3b53-03fa-49d4-835c-88623c2f4d8b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGateInitializeOr, KsGateInitializeOr function [Streaming Media Devices], avfunc_6741b878-dfae-4d40-9040-ab78d32243e2.xml, ks/KsGateInitializeOr, stream.ksgateinitializeor
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
-	KsGateInitializeOr
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateInitializeOr function


## -description


The<b> KsGateInitializeOr</b> function initializes a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure as an OR gate and attaches it to the AND gate specified by <i>NextAndGate</i>.


## -syntax


````
void __inline KsGateInitializeOr(
  _In_     PKSGATE OrGate,
  _In_opt_ PKSGATE NextAndGate
);
````


## -parameters




### -param OrGate [in]

A pointer to the KSGATE structure to initialize as a new OR gate.


### -param NextAndGate [in, optional]

A pointer to an existing KSGATE structure to which <i>OrGate</i> attaches. Optional.


## -returns



None




## -remarks



The next gate (following <i>OrGate</i>) must be an AND gate, whether it is specified in this call or later. If you need to connect an OR gate to another OR gate, use <a href="..\ks\nf-ks-ksgateinitialize.md">KsGateInitialize</a>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

This function is an inline call to <b>KsGateInitialize</b>.




## -see-also

<a href="..\ks\nf-ks-ksgateterminateand.md">KsGateTerminateAnd</a>



<a href="..\ks\nf-ks-ksgateinitialize.md">KsGateInitialize</a>



<a href="..\ks\nf-ks-ksgateterminateor.md">KsGateTerminateOr</a>



<a href="..\ks\nf-ks-ksgateinitializeand.md">KsGateInitializeAnd</a>



<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>



 

 


