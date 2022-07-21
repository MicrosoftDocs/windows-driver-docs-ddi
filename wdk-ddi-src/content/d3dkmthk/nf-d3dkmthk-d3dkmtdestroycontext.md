---
UID: NF:d3dkmthk.D3DKMTDestroyContext
title: D3DKMTDestroyContext function (d3dkmthk.h)
description: The D3DKMTDestroyContext function releases a kernel-mode device context.
old-location: display\d3dkmtdestroycontext.htm
ms.date: 02/23/2022
keywords: ["D3DKMTDestroyContext function"]
ms.keywords: D3DKMTDestroyContext, D3DKMTDestroyContext function [Display Devices], OpenGL_Functions_f7a43a18-cb8c-4b76-8123-d5eeda18d6cb.xml, d3dkmthk/D3DKMTDestroyContext, display.d3dkmtdestroycontext
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
 - D3DKMTDestroyContext
 - d3dkmthk/D3DKMTDestroyContext
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
 - D3DKMTDestroyContext
---

# D3DKMTDestroyContext function

## -description

The **D3DKMTDestroyContext** function releases a kernel-mode device context.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_DESTROYCONTEXT](ns-d3dkmthk-_d3dkmt_destroycontext.md) structure that contains the handle to the kernel-mode device context.

## -returns

**D3DKMTDestroyContext** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The device context was successfully released. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_DESTROYCONTEXT](ns-d3dkmthk-_d3dkmt_destroycontext.md)
