---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYMODE
title: "_D3DKMT_SETDISPLAYMODE"
author: windows-driver-content
description: The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display.
old-location: display\d3dkmt_setdisplaymode.htm
ms.assetid: cb590e18-59a4-4c4d-9d97-9f60c409c2e9
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMT_SETDISPLAYMODE, D3DKMT_SETDISPLAYMODE structure [Display Devices], OpenGL_Structs_05a13119-df17-4380-8c9b-8af52c989c73.xml, _D3DKMT_SETDISPLAYMODE, d3dkmthk/D3DKMT_SETDISPLAYMODE, display.d3dkmt_setdisplaymode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_SETDISPLAYMODE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETDISPLAYMODE
---

# _D3DKMT_SETDISPLAYMODE structure


## -description


The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display. 


## -struct-fields




### -field hDevice

[in] A handle to the device that requests setting of the display mode.


### -field hPrimaryAllocation

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the primary allocation for scanning out. 


### -field ScanLineOrdering

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544682">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field DisplayOrientation

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field PrivateDriverFormatAttribute

[out] A UINT value that specifies a private format attribute that the OpenGL installable client driver (ICD) should use to convert the current primary surface if a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547169">D3DKMTSetDisplayMode</a> function failed with STATUS_GRAPHICS_INCOMPATIBLE_PRIVATE_FORMAT. 


### -field Flags

Supported in Windows 7 and later versions.

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff548286">D3DKMT_SETDISPLAYMODE_FLAGS</a> structure that specifies, in bit-field flags, attributes for setting the display mode. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544682">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547169">D3DKMTSetDisplayMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548286">D3DKMT_SETDISPLAYMODE_FLAGS</a>
 

 

