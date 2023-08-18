---
UID: NS:d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX
title: D3DKMT_ACQUIREKEYEDMUTEX (d3dkmthk.h)
description: Learn more about the D3DKMT_ACQUIREKEYEDMUTEX structure.
ms.date: 07/27/2023
keywords: ["D3DKMT_ACQUIREKEYEDMUTEX structure"]
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX, D3DKMT_ACQUIREKEYEDMUTEX structure [Display Devices], OpenGL_Structs_114ed313-61ac-4c09-97fa-8b47a0aa40d1.xml, _D3DKMT_ACQUIREKEYEDMUTEX, d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX, display.d3dkmt_acquirekeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
tech.root: display
req.typenames: D3DKMT_ACQUIREKEYEDMUTEX
f1_keywords:
 - _D3DKMT_ACQUIREKEYEDMUTEX
 - d3dkmthk/_D3DKMT_ACQUIREKEYEDMUTEX
 - D3DKMT_ACQUIREKEYEDMUTEX
 - d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ACQUIREKEYEDMUTEX
 - D3DKMT_ACQUIREKEYEDMUTEX
---

# D3DKMT_ACQUIREKEYEDMUTEX structure

## -description

The **D3DKMT_ACQUIREKEYEDMUTEX** structure describes a keyed mutex that the [**D3DKMTAcquireKeyedMutex**](nf-d3dkmthk-d3dkmtacquirekeyedmutex.md) function acquires.

## -struct-fields

### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to acquire.

### -field Key

[in] A 64-bit value that specifies the key value to acquire the mutex for.

### -field pTimeout

[in] A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which acquiring the mutex is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If ***pTimeout** = 0, [**D3DKMTAcquireKeyedMutex**](nf-d3dkmthk-d3dkmtacquirekeyedmutex.md) returns without waiting. If the caller supplies a NULL pointer, **D3DKMTAcquireKeyedMutex** waits indefinitely until the mutex object is set to the signaled state.

### -field FenceValue

[out] A 64-bit value that specifies the current fence value of the GPU synchronization object.

## -see-also

[**D3DKMTAcquireKeyedMutex**](nf-d3dkmthk-d3dkmtacquirekeyedmutex.md)
