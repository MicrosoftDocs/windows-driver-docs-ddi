---
UID: NC:d3dkmthk.PFND3DKMT_CREATEDEVICE
title: PFND3DKMT_CREATEDEVICE (d3dkmthk.h)
description: The D3DKMTCreateDevice function creates a kernel-mode device context.
old-location: display\d3dkmtcreatedevice.htm
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CREATEDEVICE callback function"]
ms.keywords: D3DKMTCreateDevice, D3DKMTCreateDevice callback function [Display Devices], OpenGL_Functions_09099f43-bae3-4859-9465-434915af774a.xml, PFND3DKMT_CREATEDEVICE, PFND3DKMT_CREATEDEVICE callback, d3dkmthk/D3DKMTCreateDevice, display.d3dkmtcreatedevice
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_CREATEDEVICE
 - d3dkmthk/PFND3DKMT_CREATEDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CREATEDEVICE
---

# PFND3DKMT_CREATEDEVICE callback function


## -description

The <b>D3DKMTCreateDevice</b> function creates a kernel-mode device context.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdevice">D3DKMT_CREATEDEVICE</a> structure that describes the kernel-mode device context.

## -returns

<b>D3DKMTCreateDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The device context was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateDevice](./nf-d3dkmthk-d3dkmtcreatedevice.md)  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdevice">D3DKMT_CREATEDEVICE</a>

