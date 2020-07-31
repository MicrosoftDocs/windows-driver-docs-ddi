---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObject2
title: D3DKMTSignalSynchronizationObject2 function (d3dkmthk.h)
description: The D3DKMTSignalSynchronizationObject2 function inserts a signal for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtsignalsynchronizationobject2.htm
ms.assetid: 7a13d999-9caf-4750-beba-4e031cd0db81
ms.date: 05/10/2018
keywords: ["D3DKMTSignalSynchronizationObject2 function"]
ms.keywords: D3DKMTSignalSynchronizationObject2, D3DKMTSignalSynchronizationObject2 function [Display Devices], OpenGL_Functions_ffc87bcb-e2ab-48ea-8a90-c0b4cf7c8b33.xml, d3dkmthk/D3DKMTSignalSynchronizationObject2, display.d3dkmtsignalsynchronizationobject2
f1_keywords:
 - "d3dkmthk/D3DKMTSignalSynchronizationObject2"
 - "D3DKMTSignalSynchronizationObject2"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTSignalSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
- D3DKMTSignalSynchronizationObject2
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSignalSynchronizationObject2 function


## -description

The <b>D3DKMTSignalSynchronizationObject2</b> function inserts a signal for the specified synchronization objects in the specified context stream.

## -parameters

### -param D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobject2">D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context stream that signaling is set up for.

## -returns

<b>D3DKMTSignalSynchronizationObject2</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The signaling was successfully set up.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display context was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobject2">D3DKMT_SIGNALSYNCHRONIZATIONOBJECT2</a>
