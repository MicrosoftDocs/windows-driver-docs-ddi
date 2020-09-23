---
UID: NC:d3dkmthk.PFND3DKMT_OPENKEYEDMUTEX2
title: PFND3DKMT_OPENKEYEDMUTEX2 (d3dkmthk.h)
description: Opens a keyed mutex object that includes private data.
old-location: display\d3dkmtopenkeyedmutex2.htm
ms.assetid: 33140445-e312-4495-990a-033a87598fa1
ms.date: 05/10/2018
keywords: ["PFND3DKMT_OPENKEYEDMUTEX2 callback function"]
ms.keywords: D3DKMTOpenKeyedMutex2, D3DKMTOpenKeyedMutex2 callback function [Display Devices], PFND3DKMT_OPENKEYEDMUTEX2, PFND3DKMT_OPENKEYEDMUTEX2 callback, d3dkmthk/D3DKMTOpenKeyedMutex2, display.d3dkmtopenkeyedmutex2
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_OPENKEYEDMUTEX2
 - d3dkmthk/PFND3DKMT_OPENKEYEDMUTEX2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmthk.h
api_name:
 - D3DKMTOpenKeyedMutex2
---

# PFND3DKMT_OPENKEYEDMUTEX2 callback function


## -description

Opens a keyed mutex object that includes private data.

## -parameters

### -param Arg1

*pData* 

[in, out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openkeyedmutex2">D3DKMT_OPENKEYEDMUTEX2</a> structure that describes a keyed mutex object that includes private data.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully opened. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTOpenKeyedMutex2](./nf-d3dkmthk-d3dkmtopenkeyedmutex2.md)  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -remarks

<b>D3DKMTOpenKeyedMutex2</b> behaves like the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openkeyedmutex2">D3DKMT_OPENKEYEDMUTEX2</a>