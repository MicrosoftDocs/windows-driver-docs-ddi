---
UID: NF:d3dkmthk.D3DKMTDestroyKeyedMutex
title: D3DKMTDestroyKeyedMutex function (d3dkmthk.h)
description: The D3DKMTDestroyKeyedMutex function destroys a keyed mutex object.
old-location: display\d3dkmtdestroykeyedmutex.htm
ms.date: 02/23/2022
keywords: ["D3DKMTDestroyKeyedMutex function"]
ms.keywords: D3DKMTDestroyKeyedMutex, D3DKMTDestroyKeyedMutex function [Display Devices], OpenGL_Functions_de5400f1-6ef8-431c-a838-8c82cb03d7f1.xml, d3dkmthk/D3DKMTDestroyKeyedMutex, display.d3dkmtdestroykeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTDestroyKeyedMutex is supported beginning with the Windows 7 operating system.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTDestroyKeyedMutex
 - d3dkmthk/D3DKMTDestroyKeyedMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTDestroyKeyedMutex
---

# D3DKMTDestroyKeyedMutex function

## -description

The **D3DKMTDestroyKeyedMutex** function destroys a keyed mutex object.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_DESTROYKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_destroykeyedmutex.md) structure that specifies the keyed mutex object to destroy.

## -returns

**D3DKMTDestroyKeyedMutex** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The keyed mutex object was successfully destroyed. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_DESTROYKEYEDMUTEX](ns-d3dkmthk-_d3dkmt_destroykeyedmutex.md)
