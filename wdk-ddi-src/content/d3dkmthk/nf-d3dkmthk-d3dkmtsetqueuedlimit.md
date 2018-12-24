---
UID: NF:d3dkmthk.D3DKMTSetQueuedLimit
title: D3DKMTSetQueuedLimit function
description: The D3DKMTSetQueuedLimit function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.
old-location: display\d3dkmtsetqueuedlimit.htm
ms.assetid: 184473e4-603f-40a0-a4ea-c15d5b0b0b35
ms.date: 05/10/2018
ms.keywords: D3DKMTSetQueuedLimit, D3DKMTSetQueuedLimit function [Display Devices], OpenGL_Functions_22227369-eb8b-4ee0-a3d8-97eb0f469d94.xml, d3dkmthk/D3DKMTSetQueuedLimit, display.d3dkmtsetqueuedlimit
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSetQueuedLimit
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetQueuedLimit function

## -description

The <b>D3DKMTSetQueuedLimit</b> function sets or retrieves the limit for the number of operations of the given type that can be queued for the given device.

## -parameters

### -param D3DKMT_SETQUEUEDLIMIT

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548314">D3DKMT_SETQUEUEDLIMIT</a> structure that describes parameters for setting or retrieving the limit of queued operations.

## -returns

<b>D3DKMTSetQueuedLimit</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The limit of queued operations was successfully set or retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548225">D3DKMT_QUEUEDLIMIT_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548314">D3DKMT_SETQUEUEDLIMIT</a>
 

 

