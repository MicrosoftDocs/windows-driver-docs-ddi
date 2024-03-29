---
UID: NC:ks.PFNKSPINIRPCOMPLETION
title: PFNKSPINIRPCOMPLETION (ks.h)
description: An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.
old-location: stream\avstrminipinirpcompletion.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNKSPINIRPCOMPLETION callback function"]
ms.keywords: AVStrMiniPinIrpCompletion, AVStrMiniPinIrpCompletion routine [Streaming Media Devices], PFNKSPINIRPCOMPLETION, avstclbk_fabf9c16-a37b-4101-9468-dc247545aea0.xml, ks/AVStrMiniPinIrpCompletion, stream.avstrminipinirpcompletion
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSPINIRPCOMPLETION
 - ks/PFNKSPINIRPCOMPLETION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSPINIRPCOMPLETION
---

# PFNKSPINIRPCOMPLETION callback function


## -description

An AVStream minidriver's <i>AVStrMiniPinIrpCompletion</i> routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.

## -parameters

### -param Pin [in]


Points to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which the callback is registered.

### -param Irp [in]


Points to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> which originated from the circuit to which <i>Pin</i> belongs.

## -remarks

The minidriver specifies this routine's address in the <i>IrpCompletion</i> parameter of a call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterirpcompletioncallback">KsPinRegisterIrpCompletionCallback</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterirpcompletioncallback">KsPinRegisterIrpCompletionCallback</a>

