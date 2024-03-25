---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject
title: D3DKMTWaitForSynchronizationObject function (d3dkmthk.h)
description: The D3DKMTWaitForSynchronizationObject function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject.htm
ms.date: 03/02/2022
keywords: ["D3DKMTWaitForSynchronizationObject function"]
ms.keywords: D3DKMTWaitForSynchronizationObject, D3DKMTWaitForSynchronizationObject function [Display Devices], OpenGL_Functions_bdec46cd-1e3b-427f-8c65-df2d31171bc5.xml, d3dkmthk/D3DKMTWaitForSynchronizationObject, display.d3dkmtwaitforsynchronizationobject
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - D3DKMTWaitForSynchronizationObject
 - d3dkmthk/D3DKMTWaitForSynchronizationObject
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
 - D3DKMTWaitForSynchronizationObject
---

# D3DKMTWaitForSynchronizationObject function

## -description

The **D3DKMTWaitForSynchronizationObject** function inserts a wait for the specified synchronization objects in the specified context stream.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md) structure that describes the synchronization objects and context stream that the wait is set up for.

## -returns

**D3DKMTWaitForSynchronizationObject** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The wait was successfully set up. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display context was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_WAITFORSYNCHRONIZATIONOBJECT](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject.md)
