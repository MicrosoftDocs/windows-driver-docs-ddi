---
UID: NF:d3dkmthk.D3DKMTOpenSynchronizationObject
title: D3DKMTOpenSynchronizationObject function (d3dkmthk.h)
description: The D3DKMTOpenSynchronizationObject function opens a kernel-mode synchronization object.
old-location: display\d3dkmtopensynchronizationobject.htm
ms.date: 05/10/2018
keywords: ["D3DKMTOpenSynchronizationObject function"]
ms.keywords: D3DKMTOpenSynchronizationObject, D3DKMTOpenSynchronizationObject function [Display Devices], OpenGL_Functions_c6ae5181-a478-47d7-8f0c-49f4f5a7f318.xml, d3dkmthk/D3DKMTOpenSynchronizationObject, display.d3dkmtopensynchronizationobject
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTOpenSynchronizationObject is supported beginning with the Windows 7 operating system.
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
 - D3DKMTOpenSynchronizationObject
 - d3dkmthk/D3DKMTOpenSynchronizationObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTOpenSynchronizationObject
---

# D3DKMTOpenSynchronizationObject function


## -description

The <b>D3DKMTOpenSynchronizationObject</b> function opens a kernel-mode synchronization object.

## -parameters

### -param unnamedParam1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_opensynchronizationobject">D3DKMT_OPENSYNCHRONIZATIONOBJECT</a> structure that describes a shared synchronization object to open.

## -returns

<b>D3DKMTOpenSynchronizationObject</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode synchronization object was successfully opened. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTOpenSynchronizationObject]() could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_opensynchronizationobject">D3DKMT_OPENSYNCHRONIZATIONOBJECT</a>
