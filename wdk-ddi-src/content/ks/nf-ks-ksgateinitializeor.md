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


The<b> KsGateInitializeOr</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure as an OR gate and attaches it to the AND gate specified by <i>NextAndGate</i>.


## -parameters




### -param OrGate [in]

A pointer to the KSGATE structure to initialize as a new OR gate.


### -param NextAndGate [in, optional]

A pointer to an existing KSGATE structure to which <i>OrGate</i> attaches. Optional.


## -returns



None




## -remarks



The next gate (following <i>OrGate</i>) must be an AND gate, whether it is specified in this call or later. If you need to connect an OR gate to another OR gate, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562573">KsGateInitialize</a>. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

This function is an inline call to <b>KsGateInitialize</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562573">KsGateInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562586">KsGateTerminateAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562588">KsGateTerminateOr</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGateInitializeOr function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

