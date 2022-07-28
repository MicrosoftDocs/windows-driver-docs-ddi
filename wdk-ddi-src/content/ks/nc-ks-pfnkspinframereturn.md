---
UID: NC:ks.PFNKSPINFRAMERETURN
title: PFNKSPINFRAMERETURN (ks.h)
description: An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.
tech.root: stream
ms.date: 07/13/2022
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

## -description

An AVStream minidriver's *AVStrMiniFrameReturn* routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed.

## -parameters

### -param Pin [in]

Pointer to a [KSPIN](/windows-hardware/drivers/ddi/ks/ns-ks-_kspin) structure representing the pin on which the frame was injected.

### -param Data [in, optional]

Pointer to the buffer originally specified in the call to [KsPinSubmitFrame](/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe).

### -param Size [in, optional]

Specifies the size in bytes of*Data* as originally specified in [KsPinSubmitFrame](/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe).

### -param Mdl [in, optional]

Pointer to a memory descriptor list describing the injected frame as in the call to [KsPinSubmitFrameMdl](/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframemdl).

### -param Context [in, optional]

Pointer to the minidriver-supplied context buffer attached to the frame when the frame was injected into the circuit.

### -param Status [in]

Contains a copy of*Irp->IoStatus.Status* for the IRP to which the requested frame was attached.

## -remarks

The minidriver specifies this routine's address in the*FrameReturn* parameter of a call to [KsPinRegisterFrameReturnCallback](/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback).

## -see-also

[KsPinRegisterFrameReturnCallback](/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback)

[KsPinSubmitFrameMdl](/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframemdl)
