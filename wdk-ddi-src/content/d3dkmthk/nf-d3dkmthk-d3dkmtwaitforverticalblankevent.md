---
UID: NF:d3dkmthk.D3DKMTWaitForVerticalBlankEvent
title: D3DKMTWaitForVerticalBlankEvent function (d3dkmthk.h)
description: The D3DKMTWaitForVerticalBlankEvent function waits for the vertical blanking interval to occur and then returns.
old-location: display\d3dkmtwaitforverticalblankevent.htm
ms.date: 05/10/2018
keywords: ["D3DKMTWaitForVerticalBlankEvent function"]
ms.keywords: D3DKMTWaitForVerticalBlankEvent, D3DKMTWaitForVerticalBlankEvent function [Display Devices], OpenGL_Functions_9e2c6684-7429-43d7-b43a-0f11aea6807f.xml, d3dkmthk/D3DKMTWaitForVerticalBlankEvent, display.d3dkmtwaitforverticalblankevent
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
 - D3DKMTWaitForVerticalBlankEvent
 - d3dkmthk/D3DKMTWaitForVerticalBlankEvent
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
 - D3DKMTWaitForVerticalBlankEvent
---

# D3DKMTWaitForVerticalBlankEvent function


## -description

The <b>D3DKMTWaitForVerticalBlankEvent</b> function waits for the vertical blanking interval to occur and then returns.

## -parameters

### -param D3DKMT_WAITFORVERTICALBLANKEVENT

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforverticalblankevent">D3DKMT_WAITFORVERTICALBLANKEVENT</a> structure that describes parameters for waiting for the vertical blank to occur.

## -returns

<b>D3DKMTWaitForVerticalBlankEvent</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The vertical blanking interval successfully occurred.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other NTSTATUS values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforverticalblankevent">D3DKMT_WAITFORVERTICALBLANKEVENT</a>
