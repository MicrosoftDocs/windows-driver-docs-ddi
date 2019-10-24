---
UID: NF:d3dkmthk.D3DKMTOpenKeyedMutex2
title: D3DKMTOpenKeyedMutex2 function (d3dkmthk.h)
description: Opens a keyed mutex object that includes private data.
old-location: display\d3dkmtopenkeyedmutex2.htm
ms.assetid: 33140445-e312-4495-990a-033a87598fa1
ms.date: 05/10/2018
ms.keywords: D3DKMTOpenKeyedMutex2, D3DKMTOpenKeyedMutex2 callback function [Display Devices], PFND3DKMT_OPENKEYEDMUTEX2, PFND3DKMT_OPENKEYEDMUTEX2 callback, d3dkmthk/D3DKMTOpenKeyedMutex2, display.d3dkmtopenkeyedmutex2
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTOpenKeyedMutex2"
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
- D3DKMTOpenKeyedMutex2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenKeyedMutex2 function

## -description

Opens a keyed mutex object that includes private data.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openkeyedmutex2">D3DKMT_OPENKEYEDMUTEX2</a> structure that describes a keyed mutex object that includes private data.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully opened. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTOpenKeyedMutex2](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex2)  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -remarks

<b>D3DKMTOpenKeyedMutex2</b> behaves like the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_openkeyedmutex2">D3DKMT_OPENKEYEDMUTEX2</a>
 

 

