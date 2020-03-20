---
UID: NF:d3dkmthk.D3DKMTCreateContext
title: D3DKMTCreateContext function (d3dkmthk.h)
description: The D3DKMTCreateContext function creates a kernel-mode device context.
old-location: display\d3dkmtcreatecontext.htm
ms.assetid: e30fd034-1268-45bf-bc9c-df33e642fd4e
ms.date: 05/10/2018
keywords: ["D3DKMTCreateContext function"]
ms.keywords: D3DKMTCreateContext, D3DKMTCreateContext callback function [Display Devices], OpenGL_Functions_ee92f6d8-b9af-4171-a628-e686f190a370.xml, PFND3DKMT_CREATECONTEXT, PFND3DKMT_CREATECONTEXT callback, d3dkmthk/D3DKMTCreateContext, display.d3dkmtcreatecontext
f1_keywords:
 - "d3dkmthk/D3DKMTCreateContext"
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
api_name:
- D3DKMTCreateContext
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateContext function


## -description

The <b>D3DKMTCreateContext</b> function creates a kernel-mode device context.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createcontext">D3DKMT_CREATECONTEXT</a> structure that describes the kernel-mode device context.

## -returns

<b>D3DKMTCreateContext</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The device context was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatecontext)  could not complete because of insufficient memory. | 
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createcontext">D3DKMT_CREATECONTEXT</a>
 

 

