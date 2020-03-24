---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject2
title: D3DKMTWaitForSynchronizationObject2 function (d3dkmthk.h)
description: The D3DKMTWaitForSynchronizationObject2 function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject2.htm
ms.assetid: 692d3336-d9cd-438b-a52c-ae4c55070227
ms.date: 05/10/2018
keywords: ["D3DKMTWaitForSynchronizationObject2 function"]
ms.keywords: D3DKMTWaitForSynchronizationObject2, D3DKMTWaitForSynchronizationObject2 function [Display Devices], OpenGL_Functions_4453dc1e-8824-494e-9a74-2d3628f1ff81.xml, d3dkmthk/D3DKMTWaitForSynchronizationObject2, display.d3dkmtwaitforsynchronizationobject2
f1_keywords:
 - "d3dkmthk/D3DKMTWaitForSynchronizationObject2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTWaitForSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
- D3DKMTWaitForSynchronizationObject2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTWaitForSynchronizationObject2 function

## -description

The <b>D3DKMTWaitForSynchronizationObject2</b> function inserts a wait for the specified synchronization objects in the specified context stream.

## -parameters

### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context stream that the wait is set up for.

## -returns

<b>D3DKMTWaitForSynchronizationObject2</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The wait was successfully set up.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display context was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a>
 

 

