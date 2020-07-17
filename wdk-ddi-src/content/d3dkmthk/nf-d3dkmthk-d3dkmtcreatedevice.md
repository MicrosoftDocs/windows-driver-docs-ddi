---
UID: NF:d3dkmthk.D3DKMTCreateDevice
title: D3DKMTCreateDevice function (d3dkmthk.h)
description: The D3DKMTCreateDevice function creates a kernel-mode device context.
old-location: display\d3dkmtcreatedevice.htm
ms.assetid: 91f559cc-c84b-450d-b52c-8289e976f991
ms.date: 05/10/2018
keywords: ["D3DKMTCreateDevice function"]
ms.keywords: D3DKMTCreateDevice, D3DKMTCreateDevice callback function [Display Devices], OpenGL_Functions_09099f43-bae3-4859-9465-434915af774a.xml, PFND3DKMT_CREATEDEVICE, PFND3DKMT_CREATEDEVICE callback, d3dkmthk/D3DKMTCreateDevice, display.d3dkmtcreatedevice
f1_keywords:
 - "d3dkmthk/D3DKMTCreateDevice"
 - "D3DKMTCreateDevice"
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
- D3DKMTCreateDevice
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCreateDevice function

## -description

The <b>D3DKMTCreateDevice</b> function creates a kernel-mode device context.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdevice">D3DKMT_CREATEDEVICE</a> structure that describes the kernel-mode device context.

## -returns

<b>D3DKMTCreateDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The device context was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateDevice](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatedevice)  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdevice">D3DKMT_CREATEDEVICE</a>
 

 

