---
UID: NF:ks.KsGateInitializeAnd
title: KsGateInitializeAnd function
author: windows-driver-content
description: The KsGateInitializeAnd function initializes a KSGATE structure as an AND gate and attaches it to the OR gate specified by NextOrGate.
old-location: stream\ksgateinitializeand.htm
tech.root: stream
ms.assetid: ac03889a-1e02-4852-8ed9-487674c6e0de
ms.date: 04/23/2018
ms.keywords: KsGateInitializeAnd, KsGateInitializeAnd function [Streaming Media Devices], avfunc_9eb102c9-08f4-44f7-bc3e-889aa8f85f23.xml, ks/KsGateInitializeAnd, stream.ksgateinitializeand
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
-	KsGateInitializeAnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateInitializeAnd function


## -description


The<b> KsGateInitializeAnd</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure as an AND gate and attaches it to the OR gate specified by <i>NextOrGate</i>.


## -parameters




### -param AndGate [in]

A pointer to the KSGATE structure to initialize as a new AND gate.


### -param NextOrGate [in, optional]

A pointer to an existing KSGATE structure to which <i>AndGate</i> attaches. This parameter should be an OR gate and is optional.


## -returns



None




## -remarks



The next gate (following <i>AndGate</i>) must be an OR gate, whether it is specified in this call or later. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

<b>KsGateInitializeAnd</b> is an inline call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562573">KsGateInitialize</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562573">KsGateInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562586">KsGateTerminateAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562588">KsGateTerminateOr</a>
 

 

