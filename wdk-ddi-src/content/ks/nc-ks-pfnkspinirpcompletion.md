---
UID: NC:ks.PFNKSPINIRPCOMPLETION
title: PFNKSPINIRPCOMPLETION
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.
old-location: stream\avstrminipinirpcompletion.htm
tech.root: stream
ms.assetid: 46b29026-b3a9-49cc-8f3d-0318516526d2
ms.date: 04/23/2018
ms.keywords: AVStrMiniPinIrpCompletion, AVStrMiniPinIrpCompletion routine [Streaming Media Devices], PFNKSPINIRPCOMPLETION, avstclbk_fabf9c16-a37b-4101-9468-dc247545aea0.xml, ks/AVStrMiniPinIrpCompletion, stream.avstrminipinirpcompletion
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniPinIrpCompletion
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPINIRPCOMPLETION callback function


## -description


An AVStream minidriver's <i>AVStrMiniPinIrpCompletion</i> routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.


## -parameters




### -param Pin [in]

Points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which the callback is registered.


### -param Irp [in]

Points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> which originated from the circuit to which <i>Pin</i> belongs.


## -returns



None




## -remarks



The minidriver specifies this routine's address in the <i>IrpCompletion</i> parameter of a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff563524">KsPinRegisterIrpCompletionCallback</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563524">KsPinRegisterIrpCompletionCallback</a>
 

 

