---
UID: NF:d3dkmthk.D3DKMTEscape
title: D3DKMTEscape function (d3dkmthk.h)
description: The D3DKMTEscape function exchanges information with the display miniport driver.
old-location: display\d3dkmtescape.htm
ms.assetid: 60b105df-2085-40bc-9d95-0f6b317a565e
ms.date: 05/10/2018
keywords: ["D3DKMTEscape function"]
ms.keywords: D3DKMTEscape, D3DKMTEscape function [Display Devices], OpenGL_Functions_ad391641-4fb5-425a-839f-7b257f26849a.xml, d3dkmthk/D3DKMTEscape, display.d3dkmtescape
f1_keywords:
 - "d3dkmthk/D3DKMTEscape"
 - "D3DKMTEscape"
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTEscape function


## -description

The <b>D3DKMTEscape</b> function exchanges information with the display miniport driver.

## -parameters

### -param D3DKMT_ESCAPE

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a> structure that describes the exchanged information.

## -returns

<b>D3DKMTEscape</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | Information was successfully shared. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTEscape](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape)  could not complete because of insufficient memory. | 
| **STATUS_PRIVILEGED_INSTRUCTION** | [D3DKMTEscape](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape)  detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current CPU process). | 
| **STATUS_ILLEGAL_INSTRUCTION** | [D3DKMTEscape](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtescape)  detected instructions that cannot be supported by graphics hardware. | 

This function might also return other <b>NTSTATUS</b> values.

## -remarks

The OpenGL ICD calls <b>D3DKMTEscape</b> to exchange data directly with the display miniport driver. For testing purposes, the OpenGL ICD can also call <b>D3DKMTEscape</b> to control the video memory manager and graphics processing unit (GPU) scheduler (which are part of <i>Dxgkrnl.sys</i>) and the behavior of the operating system's Timeout Detection and Recovery (TDR) process. 

Hardware vendors can use <b>D3DKMTEscape</b> in their OpenGL ICDs as an extension mechanism. However, vendors should report necessary extensions to Microsoft so the extensions can be natively supported by the operating system.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_escape">D3DKMT_ESCAPE</a>
