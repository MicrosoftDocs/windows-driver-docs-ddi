---
UID: NS:d3dkmthk._D3DKMT_ACQUIREKEYEDMUTEX2
title: D3DKMT_ACQUIREKEYEDMUTEX2 (d3dkmthk.h)
description: Learn more about the D3DKMTAcquireKeyedMutex2 function.
ms.date: 07/27/2023
keywords: ["D3DKMT_ACQUIREKEYEDMUTEX2 structure"]
ms.keywords: D3DKMT_ACQUIREKEYEDMUTEX2, D3DKMT_ACQUIREKEYEDMUTEX2 structure [Display Devices], _D3DKMT_ACQUIREKEYEDMUTEX2, d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX2, display.d3dkmt_acquirekeyedmutex2
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: D3DKMT_ACQUIREKEYEDMUTEX2
f1_keywords:
 - _D3DKMT_ACQUIREKEYEDMUTEX2
 - d3dkmthk/_D3DKMT_ACQUIREKEYEDMUTEX2
 - D3DKMT_ACQUIREKEYEDMUTEX2
 - d3dkmthk/D3DKMT_ACQUIREKEYEDMUTEX2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_ACQUIREKEYEDMUTEX2
 - D3DKMT_ACQUIREKEYEDMUTEX2
---

# D3DKMT_ACQUIREKEYEDMUTEX2 structure

## -description

Describes a keyed mutex object that the [**D3DKMTAcquireKeyedMutex2**](nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md) function acquires that includes private data.

## -struct-fields

### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a handle to the keyed mutex.

### -field Key

[in] The key value to acquire.

### -field pTimeout

[in] An NT-style timeout value.

### -field FenceValue

[out] The current fence value of the GPU sync object.

### -field pPrivateRuntimeData

[out] A pointer to a buffer to copy private data to.

### -field PrivateRuntimeDataSize

[in] The size, in bytes, of the **pPrivateRuntimeData** member.

## -see-also

[**D3DKMTAcquireKeyedMutex2**](nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md)
