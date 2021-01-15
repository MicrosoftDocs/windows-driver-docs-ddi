---
UID: NC:ks.PFNKSPINFRAMERETURN
title: PFNKSPINFRAMERETURN (ks.h)
description: An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.
old-location: stream\avstrminiframereturn.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNKSPINFRAMERETURN callback function"]
ms.keywords: AVStrMiniFrameReturn, AVStrMiniFrameReturn routine [Streaming Media Devices], PFNKSPINFRAMERETURN, avstclbk_e7edb74a-8c38-4e7d-9978-849e5d88c153.xml, ks/AVStrMiniFrameReturn, stream.avstrminiframereturn
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSPINFRAMERETURN
 - ks/PFNKSPINFRAMERETURN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSPINFRAMERETURN
---

# PFNKSPINFRAMERETURN callback function


## -description

An AVStream minidriver's <i>AVStrMiniFrameReturn</i> routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.

## -parameters

### -param Pin 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure representing the pin on which the frame was injected.

### -param Data 

[in, optional]
Pointer to the buffer originally specified in the call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe">KsPinSubmitFrame</a>.

### -param OPTIONAL

### -param Mdl 

[in, optional]
Pointer to a memory descriptor list describing the injected frame as in the call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframemdl">KsPinSubmitFrameMdl</a><b>.</b>

### -param Context 

[in, optional]
Pointer to the minidriver-supplied context buffer attached to the frame when the frame was injected into the circuit.

### -param Status 

[in]
Contains a copy of <i>Irp->IoStatus.Status</i> for the IRP to which the requested frame was attached.


#### - Size [in, optional]

Specifies the size in bytes of <i>Data</i> as originally specified in <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe">KsPinSubmitFrame</a>.

## -remarks

The minidriver specifies this routine's address in the <i>FrameReturn</i> parameter of a call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframemdl">KsPinSubmitFrameMdl</a>

