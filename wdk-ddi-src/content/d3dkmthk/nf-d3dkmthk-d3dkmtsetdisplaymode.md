---
UID: NF:d3dkmthk.D3DKMTSetDisplayMode
title: D3DKMTSetDisplayMode function (d3dkmthk.h)
description: The D3DKMTSetDisplayMode function sets the allocation that is used to scan out to the display.
old-location: display\d3dkmtsetdisplaymode.htm
ms.date: 03/01/2022
keywords: ["D3DKMTSetDisplayMode function"]
ms.keywords: D3DKMTSetDisplayMode, D3DKMTSetDisplayMode function [Display Devices], OpenGL_Functions_dc92e1c9-5873-42b6-a8f8-f6827091dac4.xml, d3dkmthk/D3DKMTSetDisplayMode, display.d3dkmtsetdisplaymode
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
 - D3DKMTSetDisplayMode
 - d3dkmthk/D3DKMTSetDisplayMode
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
 - D3DKMTSetDisplayMode
---

# D3DKMTSetDisplayMode function

## -description

The **D3DKMTSetDisplayMode** function sets the allocation that is used to scan out to the display.

## -parameters

### -param unnamedParam1 [in, out]

A pointer to a [D3DKMT_SETDISPLAYMODE](ns-d3dkmthk-_d3dkmt_setdisplaymode.md) structure that describes the allocation that is used to scan out.

## -returns

**D3DKMTSetDisplayMode** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The display mode was successfully set. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |
| STATUS_GRAPHICS_NOT_EXCLUSIVE_MODE_OWNER | Before the call to **D3DKMTSetDisplayMode**, the device did not acquire exclusive ownership of the view. Therefore, the device could not set the display mode. |
| D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT | The OpenGL installable client driver (ICD) must convert the format of the surface that is associated with the allocation that the *hPrimaryAllocation* member of [D3DKMT_SETDISPLAYMODE](ns-d3dkmthk-_d3dkmt_setdisplaymode.md) specifies into the format attribute that the *PrivateDriverFormatAttribute* member of **D3DKMT_SETDISPLAYMODE** specifies. The ICD should then call **D3DKMTSetDisplayMode** again. The ICD could allocate a new allocation, perform a conversion bit-block transfer (bitblt) from the old primary to the new, and then destroy the old primary as long as the ICD uses the new allocation handle for this allocation for all subsequent operations. The ICD should repeat this process until **D3DKMTSetDisplayMode** returns a different return value. |

This function might also return other **NTSTATUS** values.

## -remarks

Before the OpenGL ICD calls **D3DKMTSetDisplayMode** to set a new display mode that uses an extended format, a multiple-sampling method, or both, the ICD must ensure that the current GDI display mode has the same resolution as the new display mode. Otherwise, **D3DKMTSetDisplayMode** returns **STATUS_INVALID_PARAMETER**.

## -see-also

[D3DKMT_SETDISPLAYMODE](ns-d3dkmthk-_d3dkmt_setdisplaymode.md)