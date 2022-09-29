---
UID: NC:d3dkmthk.PFND3DKMT_ACQUIREKEYEDMUTEX
title: PFND3DKMT_ACQUIREKEYEDMUTEX (d3dkmthk.h)
description: The PFND3DKMT_ACQUIREKEYEDMUTEX callback function acquires a keyed mutex object. The function returns STATUS_SUCCESS if the keyed mutex object was successfully acquired.
old-location: display\d3dkmtacquirekeyedmutex.htm
ms.date: 03/03/2022
keywords: ["PFND3DKMT_ACQUIREKEYEDMUTEX callback function"]
ms.keywords: D3DKMTAcquireKeyedMutex, D3DKMTAcquireKeyedMutex callback function [Display Devices], OpenGL_Functions_547da245-f41b-4e73-bf9c-7a72f6104def.xml, PFND3DKMT_ACQUIREKEYEDMUTEX, PFND3DKMT_ACQUIREKEYEDMUTEX callback, d3dkmthk/D3DKMTAcquireKeyedMutex, display.d3dkmtacquirekeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTAcquireKeyedMutex is supported beginning with the Windows 7 operating system.
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
req.typenames: 
f1_keywords:
 - PFND3DKMT_ACQUIREKEYEDMUTEX
 - d3dkmthk/PFND3DKMT_ACQUIREKEYEDMUTEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_ACQUIREKEYEDMUTEX
---

# PFND3DKMT_ACQUIREKEYEDMUTEX callback function

## -description

The **D3DKMTAcquireKeyedMutex** function acquires a keyed mutex object.

## -parameters

### -param unnamedParam1 [in, out]

A pointer to a [D3DKMT_ACQUIREKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md) structure that specifies the keyed mutex object to acquire.

## -returns

**D3DKMTAcquireKeyedMutex** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The keyed mutex object was successfully acquired. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_NO_MEMORY | [D3DKMTAcquireKeyedMutex](nf-d3dkmthk-d3dkmtacquirekeyedmutex.md) could not complete because of insufficient memory. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_ACQUIREKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md)
