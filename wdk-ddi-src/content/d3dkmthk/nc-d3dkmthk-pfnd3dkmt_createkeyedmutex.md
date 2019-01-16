---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX
title: PFND3DKMT_CREATEKEYEDMUTEX
description: The D3DKMTCreateKeyedMutex function creates a keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
ms.assetid: ae9e4771-ba8d-4472-aeb8-04c3f3c59efa
ms.date: 05/10/2018
ms.keywords: D3DKMTCreateKeyedMutex, D3DKMTCreateKeyedMutex callback function [Display Devices], OpenGL_Functions_a8475da1-40bf-4669-9da8-f6bb09c3f905.xml, PFND3DKMT_CREATEKEYEDMUTEX, PFND3DKMT_CREATEKEYEDMUTEX callback, d3dkmthk/D3DKMTCreateKeyedMutex, display.d3dkmtcreatekeyedmutex
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTCreateKeyedMutex
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_CREATEKEYEDMUTEX callback function

## -description

The <b>D3DKMTCreateKeyedMutex</b> function creates a keyed mutex object.

## -parameters

### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547834">D3DKMT_CREATEKEYEDMUTEX</a> structure that describes a keyed mutex object to create. 

## -returns

<b>D3DKMTCreateKeyedMutex</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully created. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTCreateKeyedMutex](https://msdn.microsoft.com/library/windows/hardware/ff546845)  could not complete because of insufficient memory. |  

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547834">D3DKMT_CREATEKEYEDMUTEX</a>
 
