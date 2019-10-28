---
UID: NF:d3dkmthk.D3DKMTSetDisplayMode
title: D3DKMTSetDisplayMode function (d3dkmthk.h)
description: The D3DKMTSetDisplayMode function sets the allocation that is used to scan out to the display.
old-location: display\d3dkmtsetdisplaymode.htm
ms.assetid: bf51b8dc-82e8-420e-bc3d-7cb9e8d72b9f
ms.date: 05/10/2018
ms.keywords: D3DKMTSetDisplayMode, D3DKMTSetDisplayMode function [Display Devices], OpenGL_Functions_dc92e1c9-5873-42b6-a8f8-f6827091dac4.xml, d3dkmthk/D3DKMTSetDisplayMode, display.d3dkmtsetdisplaymode
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTSetDisplayMode"
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
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetDisplayMode function


## -description


The <i>D3DKMTSetDisplayMode</i> function sets the allocation that is used to scan out to the display.


## -parameters




### -param D3DKMT_SETDISPLAYMODE






*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplaymode">D3DKMT_SETDISPLAYMODE</a> structure that describes the allocation that is used to scan out.


## -returns



<i>D3DKMTSetDisplayMode</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The display mode was successfully set. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_GRAPHICS_NOT_EXCLUSIVE_MODE_OWNER** |     Before the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a>, the device did not acquire exclusive ownership of the view; therefore, the device could not set the display mode.|
| **D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT** | The OpenGL installable client driver (ICD) must convert the format of the surface that is associated with the allocation that the hPrimaryAllocation member of [D3DKMT_SETDISPLAYMODE](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplaymode)  specifies into the format attribute that the PrivateDriverFormatAttribute member of D3DKMT_SETDISPLAYMODE specifies. The ICD should then call [D3DKMTSetDisplayMode](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode)  again. The ICD could allocate a new allocation, perform a conversion bit-block transfer (bitblt) from the old primary to the new, and then destroy the old primary as long as the ICD uses the new allocation handle for this allocation for all subsequent operations. The ICD should repeat this process until D3DKMTSetDisplayMode returns a different return value. |

This function might also return other NTSTATUS values.




## -remarks



Before the OpenGL ICD calls 
      <i>D3DKMTSetDisplayMode</i> to set a new display mode that uses an extended format, a multiple-sampling method, or both, the ICD must ensure that the current GDI display mode has the same resolution as the new display mode; otherwise, 
      <i>D3DKMTSetDisplayMode</i> returns <b>STATUS_INVALID_PARAMETER</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplaymode">D3DKMT_SETDISPLAYMODE</a>
 

 

