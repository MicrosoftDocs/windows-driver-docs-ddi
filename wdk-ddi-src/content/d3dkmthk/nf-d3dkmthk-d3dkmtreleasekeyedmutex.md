---
UID: NF:d3dkmthk.D3DKMTReleaseKeyedMutex
title: D3DKMTReleaseKeyedMutex function (d3dkmthk.h)
description: The D3DKMTReleaseKeyedMutex function releases a keyed mutex object.
old-location: display\d3dkmtreleasekeyedmutex.htm
ms.assetid: c2a50621-fa84-4525-86f7-845e886203fe
ms.date: 05/10/2018
keywords: ["D3DKMTReleaseKeyedMutex function"]
ms.keywords: D3DKMTReleaseKeyedMutex, D3DKMTReleaseKeyedMutex function [Display Devices], OpenGL_Functions_16fd3037-2615-49c0-8500-7c93bcda3c9f.xml, d3dkmthk/D3DKMTReleaseKeyedMutex, display.d3dkmtreleasekeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTReleaseKeyedMutex is supported beginning with the Windows 7 operating system.
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
 - D3DKMTReleaseKeyedMutex
 - d3dkmthk/D3DKMTReleaseKeyedMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-DX-D3DKmt-l1-1-0.dll
 - API-MS-Win-DX-D3DKmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTReleaseKeyedMutex
---

# D3DKMTReleaseKeyedMutex function


## -description

The <b>D3DKMTReleaseKeyedMutex</b> function releases a keyed mutex object.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_releasekeyedmutex">D3DKMT_RELEASEKEYEDMUTEX</a> structure that specifies the keyed mutex object to release.

## -returns

<b>D3DKMTReleaseKeyedMutex</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The keyed mutex object was successfully released. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTReleaseKeyedMutex]()  could not complete because of insufficient memory. | 

This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_releasekeyedmutex">D3DKMT_RELEASEKEYEDMUTEX</a>