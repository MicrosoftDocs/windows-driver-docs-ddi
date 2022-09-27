---
UID: NF:ks.KsPinSubmitFrame
title: KsPinSubmitFrame function (ks.h)
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit.
tech.root: stream
ms.date: 07/13/2022
keywords: ["KsPinSubmitFrame function"]
ms.keywords: KsPinSubmitFrame, KsPinSubmitFrame function [Streaming Media Devices], avfunc_ce7c4c71-c404-4061-a2e5-b9f4c15df4a2.xml, ks/KsPinSubmitFrame, stream.kspinsubmitframe
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinSubmitFrame
 - ks/KsPinSubmitFrame
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinSubmitFrame
---

## -description

If a pin has been placed into injection mode by a call to [KsPinRegisterFrameReturnCallback](./nf-ks-kspinregisterframereturncallback.md), the **KsPinSubmitFrame** function submits a frame directly into the transport circuit.

## -parameters

### -param Pin [in]

A pointer to the [KSPIN](./ns-ks-_kspin.md) structure on which to submit a frame.

### -param Data [in, optional]

A pointer to a frame buffer. This should be **NULL** if and only if *Size* is equal to 0. Optional.

### -param Size [in, optional]

The size in bytes of the frame buffer to which the *Data* field points. If the *Data* field is **NULL**, set this parameter to zero. Optional.

### -param StreamHeader [in, optional]

A pointer to a [KSSTREAM_HEADER](./ns-ks-ksstream_header.md) structure. The stream header is copied if this parameter is supplied. Optional.

### -param Context [in, optional]

A pointer to a caller-allocated buffer. AVStream provides this pointer to the frame return callback registered through a call to [KsPinRegisterFrameReturnCallback](./nf-ks-kspinregisterframereturncallback.md). Optional.

## -returns

Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.

## -see-also

[KsPinRegisterFrameReturnCallback](./nf-ks-kspinregisterframereturncallback.md)

[KsPinSubmitFrameMdl](./nf-ks-kspinsubmitframemdl.md)