---
UID: NF:d3dkmthk.D3DKMTCreateKeyedMutex
title: D3DKMTCreateKeyedMutex function (d3dkmthk.h)
description: The D3DKMTCreateKeyedMutex function creates a keyed mutex object. The function returns STATUS_SUCCESS on successful creation of the keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
ms.date: 05/10/2018
keywords: ["D3DKMTCreateKeyedMutex function"]
ms.keywords: D3DKMTCreateKeyedMutex, D3DKMTCreateKeyedMutex callback function [Display Devices], OpenGL_Functions_a8475da1-40bf-4669-9da8-f6bb09c3f905.xml, PFND3DKMT_CREATEKEYEDMUTEX, PFND3DKMT_CREATEKEYEDMUTEX callback, d3dkmthk/D3DKMTCreateKeyedMutex, display.d3dkmtcreatekeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateKeyedMutex is supported beginning with the Windows 7 operating system.
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
 - D3DKMTCreateKeyedMutex
 - d3dkmthk/D3DKMTCreateKeyedMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTCreateKeyedMutex
---

# D3DKMTCreateKeyedMutex function


## -description

The <b>D3DKMTCreateKeyedMutex</b> function creates a keyed mutex object.

## -parameters

### -param unnamedParam1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex">D3DKMT_CREATEKEYEDMUTEX</a> structure that describes a keyed mutex object to create.

## -returns

<b>D3DKMTCreateKeyedMutex</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateKeyedMutex]()  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex">D3DKMT_CREATEKEYEDMUTEX</a>
