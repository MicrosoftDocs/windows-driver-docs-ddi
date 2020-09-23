---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX
title: PFND3DKMT_CREATEKEYEDMUTEX (d3dkmthk.h)
description: The D3DKMTCreateKeyedMutex function creates a keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
ms.assetid: ae9e4771-ba8d-4472-aeb8-04c3f3c59efa
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CREATEKEYEDMUTEX callback function"]
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
 - D3DKMTCreateKeyedMutex
---

# PFND3DKMT_CREATEKEYEDMUTEX callback function


## -description

The <b>D3DKMTCreateKeyedMutex</b> function creates a keyed mutex object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex">D3DKMT_CREATEKEYEDMUTEX</a> structure that describes a keyed mutex object to create.

## -returns

<b>D3DKMTCreateKeyedMutex</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateKeyedMutex](./nf-d3dkmthk-d3dkmtcreatekeyedmutex.md)  could not complete because of insufficient memory. |  

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex">D3DKMT_CREATEKEYEDMUTEX</a>