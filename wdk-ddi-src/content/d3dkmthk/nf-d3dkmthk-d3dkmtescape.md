---
UID: NF:d3dkmthk.D3DKMTEscape
title: D3DKMTEscape function (d3dkmthk.h)
description: The D3DKMTEscape function exchanges information with the display miniport driver.
old-location: display\d3dkmtescape.htm
ms.date: 02/25/2022
keywords: ["D3DKMTEscape function"]
ms.keywords: D3DKMTEscape, D3DKMTEscape function [Display Devices], OpenGL_Functions_ad391641-4fb5-425a-839f-7b257f26849a.xml, d3dkmthk/D3DKMTEscape, display.d3dkmtescape
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - D3DKMTEscape
 - d3dkmthk/D3DKMTEscape
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
 - D3DKMTEscape
---

# D3DKMTEscape function

## -description

The **D3DKMTEscape** function exchanges information with the display miniport driver.

## -parameters

### -param unnamedParam1 [in]

A pointer to a structure that describes the exchanged information.

## -returns

**D3DKMTEscape** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | Information was successfully shared. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_NO_MEMORY | **D3DKMTEscape** could not complete because of insufficient memory. |
| STATUS_PRIVILEGED_INSTRUCTION | **D3DKMTEscape** detected non-privileged instructions (that is, instructions that access memory beyond the privilege of the current CPU process). |
| STATUS_ILLEGAL_INSTRUCTION | **D3DKMTEscape** detected instructions that cannot be supported by graphics hardware. |

This function might also return other **NTSTATUS** values.

## -remarks

The OpenGL ICD calls **D3DKMTEscape** to exchange data directly with the display miniport driver. For testing purposes, the OpenGL ICD can also call **D3DKMTEscape** to control the video memory manager and graphics processing unit (GPU) scheduler (which are part of *Dxgkrnl.sys*) and the behavior of the operating system's Timeout Detection and Recovery (TDR) process.

Hardware vendors can use **D3DKMTEscape** in their OpenGL ICDs as an extension mechanism. However, vendors should report necessary extensions to Microsoft so the extensions can be natively supported by the operating system.

## -see-also

[D3DKMT_ESCAPE](ns-d3dkmthk-_d3dkmt_escape.md)
