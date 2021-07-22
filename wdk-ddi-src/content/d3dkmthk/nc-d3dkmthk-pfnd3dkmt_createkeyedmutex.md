---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX
title: PFND3DKMT_CREATEKEYEDMUTEX (d3dkmthk.h)
description: The PFND3DKMT_CREATEKEYEDMUTEX callback creates a keyed mutex object. The function returns STATUS_SUCCESS on successful creation of the keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
ms.date: 04/01/2021
keywords: ["PFND3DKMT_CREATEKEYEDMUTEX callback function"]
ms.keywords: D3DKMTCreateKeyedMutex, D3DKMTCreateKeyedMutex callback function [Display Devices], OpenGL_Functions_a8475da1-40bf-4669-9da8-f6bb09c3f905.xml, PFND3DKMT_CREATEKEYEDMUTEX, PFND3DKMT_CREATEKEYEDMUTEX callback, d3dkmthk/D3DKMTCreateKeyedMutex, display.d3dkmtcreatekeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.typenames: 
f1_keywords:
 - PFND3DKMT_CREATEKEYEDMUTEX
 - d3dkmthk/PFND3DKMT_CREATEKEYEDMUTEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEKEYEDMUTEX
---

# PFND3DKMT_CREATEKEYEDMUTEX callback function

## -description

The **D3DKMTCreateKeyedMutex** function creates a keyed mutex object.

## -parameters

### -param unnamedParam1

*pData* [in, out]

A pointer to a [**D3DKMT_CREATEKEYEDMUTEX**](ns-d3dkmthk-_d3dkmt_createkeyedmutex.md) structure that describes a keyed mutex object to create.

## -returns

**D3DKMTCreateKeyedMutex** returns an NTSTATUS code such as one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS           | The keyed mutex object was successfully created. |
| STATUS_DEVICE_REMOVED    | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_NO_MEMORY         | [D3DKMTCreateKeyedMutex](./nf-d3dkmthk-d3dkmtcreatekeyedmutex.md) could not complete because of insufficient memory. |

## -see-also

[**D3DKMT_CREATEKEYEDMUTEX**](ns-d3dkmthk-_d3dkmt_createkeyedmutex.md)
