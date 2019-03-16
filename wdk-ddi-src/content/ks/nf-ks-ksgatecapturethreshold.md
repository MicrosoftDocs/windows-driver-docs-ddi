---
UID: NF:ks.KsGateCaptureThreshold
title: KsGateCaptureThreshold function (ks.h)
description: The KsGateCaptureThreshold function is used to capture an ON input of an AND gate specified by Gate.
old-location: stream\ksgatecapturethreshold.htm
tech.root: stream
ms.assetid: 24a7745d-28f8-4f5a-9f51-37ad2d0ffa0b
ms.date: 04/23/2018
ms.keywords: KsGateCaptureThreshold, KsGateCaptureThreshold function [Streaming Media Devices], avfunc_9fd4ddfc-f715-45da-936e-9527b8ec4a25.xml, ks/KsGateCaptureThreshold, stream.ksgatecapturethreshold
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
- KsGateCaptureThreshold
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateCaptureThreshold function


## -description


The<b> KsGateCaptureThreshold</b> function is used to capture an ON input of an AND gate specified by <i>Gate</i>.


## -parameters




### -param Gate [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure representing the AND gate for which to capture an ON input synchronously.


## -returns



<b>KsGateCaptureThreshold</b> returns <b>TRUE</b> if the AND gate was originally open. Note that returning <b>TRUE</b> implies that the gate was closed so that no other thread could simultaneously capture the gate and commence processing.




## -remarks



<b>KsGateCaptureThreshold</b> checks the state of the given AND gate. If the gate is open, it turns off an input to the gate, thereby transitioning the gate to a closed state. If the gate is closed, the function does nothing. Unlike <b>KsGateGetStateUnsafe</b>, this call is done synchronously with respect to other gate state changes. It is the primary synchronization mechanism for processing based on gate control.

Despite its name, this function is only a valid call for AND gates, not gates in general. AVStream, however, does not verify whether <i>Gate</i> is an AND gate or an OR gate. It is the caller's responsibility to ensure that the call is only made on AND gates.

The call is made using interlocked functions and is thus synchronous with respect to any of the other gate state change functions; it is also a very efficient method of process control. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562567">KsGateAddOffInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562568">KsGateAddOffInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562569">KsGateAddOnInputToAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562570">KsGateAddOnInputToOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562572">KsGateGetStateUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562578">KsGateRemoveOffInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562580">KsGateRemoveOffInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562584">KsGateRemoveOnInputFromAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562585">KsGateRemoveOnInputFromOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562589">KsGateTurnInputOff</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562591">KsGateTurnInputOn</a>
 

 

