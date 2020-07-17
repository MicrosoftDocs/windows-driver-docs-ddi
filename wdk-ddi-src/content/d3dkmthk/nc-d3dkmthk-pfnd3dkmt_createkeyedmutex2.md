---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX2
title: PFND3DKMT_CREATEKEYEDMUTEX2 (d3dkmthk.h)
description: Creates a keyed mutex object that includes private data.
old-location: display\d3dkmtcreatekeyedmutex2.htm
ms.assetid: fedd7aa0-366c-4083-b6d2-692332813b3f
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CREATEKEYEDMUTEX2 callback function"]
ms.keywords: D3DKMTCreateKeyedMutex2, D3DKMTCreateKeyedMutex2 callback function [Display Devices], PFND3DKMT_CREATEKEYEDMUTEX2, PFND3DKMT_CREATEKEYEDMUTEX2 callback, d3dkmthk/D3DKMTCreateKeyedMutex2, display.d3dkmtcreatekeyedmutex2
f1_keywords:
 - "d3dkmthk/D3DKMTCreateKeyedMutex2"
 - "D3DKMTCreateKeyedMutex2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmthk.h
api_name:
- D3DKMTCreateKeyedMutex2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_CREATEKEYEDMUTEX2 callback function

## -description

Creates a keyed mutex object that includes private data.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2">D3DKMT_CREATEKEYEDMUTEX2</a> structure that describes a keyed mutex object to create.

## -returns

Returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully created. |
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. |
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. |
| **STATUS_NO_MEMORY** | [D3DKMTCreateKeyedMutex2](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex2)  could not complete because of insufficient memory. |

This function might also return other NTSTATUS values.

## -remarks

<b>D3DKMTCreateKeyedMutex2</b> behaves like the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex">D3DKMTCreateKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

Keyed mutexes created with <b>D3DKMTCreateKeyedMutex2</b> are still compatible with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex">D3DKMTAcquireKeyedMutex</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtreleasekeyedmutex">D3DKMTReleaseKeyedMutex</a> functions.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtacquirekeyedmutex">D3DKMTAcquireKeyedMutex</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatekeyedmutex">D3DKMTCreateKeyedMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtreleasekeyedmutex">D3DKMTReleaseKeyedMutex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createkeyedmutex2">D3DKMT_CREATEKEYEDMUTEX2</a>
 

 

