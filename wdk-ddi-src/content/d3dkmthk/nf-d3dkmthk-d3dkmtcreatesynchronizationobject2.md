---
UID: NF:d3dkmthk.D3DKMTCreateSynchronizationObject2
title: D3DKMTCreateSynchronizationObject2 function (d3dkmthk.h)
description: Learn more about the D3DKMTCreateSynchronizationObject2 function.
ms.date: 03/14/2024
keywords: ["D3DKMTCreateSynchronizationObject2 function"]
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
 - D3DKMTCreateSynchronizationObject2
 - d3dkmthk/D3DKMTCreateSynchronizationObject2
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
 - D3DKMTCreateSynchronizationObject2
---

# D3DKMTCreateSynchronizationObject2 function

## -description

The **D3DKMTCreateSynchronizationObject2** function creates a kernel-mode synchronization object.

## -parameters

### -param unnamedParam1

**pData** [in/out] is a pointer to a [**D3DKMT_CREATESYNCHRONIZATIONOBJECT2**](ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md) structure that describes the synchronization object to create.

## -returns

**D3DKMTCreateSynchronizationObject2** returns an **NTSTATUS** value such as one of the following:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode synchronization object was successfully created. |
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. |
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. |
| **STATUS_NO_MEMORY** | **D3DKMTCreateSynchronizationObject2** couldn't complete because of insufficient memory. |

## -see-also

[**D3DKMT_CREATESYNCHRONIZATIONOBJECT2**](ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md)
