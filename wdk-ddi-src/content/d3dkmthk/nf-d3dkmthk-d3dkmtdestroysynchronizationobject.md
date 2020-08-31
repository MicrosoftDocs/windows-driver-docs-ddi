---
UID: NF:d3dkmthk.D3DKMTDestroySynchronizationObject
title: D3DKMTDestroySynchronizationObject function (d3dkmthk.h)
description: The D3DKMTDestroySynchronizationObject function destroys a kernel-mode synchronization object.
old-location: display\d3dkmtdestroysynchronizationobject.htm
ms.assetid: 38e77d21-a386-4de8-8d1c-db48434828c6
ms.date: 05/10/2018
keywords: ["D3DKMTDestroySynchronizationObject function"]
ms.keywords: D3DKMTDestroySynchronizationObject, D3DKMTDestroySynchronizationObject function [Display Devices], OpenGL_Functions_181e72ed-9dd7-4b4c-b6e6-9231a2603f20.xml, d3dkmthk/D3DKMTDestroySynchronizationObject, display.d3dkmtdestroysynchronizationobject
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTDestroySynchronizationObject
 - d3dkmthk/D3DKMTDestroySynchronizationObject
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
 - D3DKMTDestroySynchronizationObject
---

# D3DKMTDestroySynchronizationObject function


## -description

The <b>D3DKMTDestroySynchronizationObject</b> function destroys a kernel-mode synchronization object.

## -parameters

### -param D3DKMT_DESTROYSYNCHRONIZATIONOBJECT

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroysynchronizationobject">D3DKMT_DESTROYSYNCHRONIZATIONOBJECT</a> structure that contains the handle to the synchronization object to destroy.

## -returns

<b>D3DKMTDestroySynchronizationObject</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The kernel-mode overlay object was successfully destroyed.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroysynchronizationobject">D3DKMT_DESTROYSYNCHRONIZATIONOBJECT</a>

