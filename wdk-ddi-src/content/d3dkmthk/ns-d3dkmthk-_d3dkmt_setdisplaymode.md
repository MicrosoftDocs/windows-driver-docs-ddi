---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYMODE
title: "_D3DKMT_SETDISPLAYMODE"
author: windows-driver-content
description: The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display.
old-location: display\d3dkmt_setdisplaymode.htm
old-project: display
ms.assetid: cb590e18-59a4-4c4d-9d97-9f60c409c2e9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_SETDISPLAYMODE structure [Display Devices], D3DKMT_SETDISPLAYMODE, d3dkmthk/D3DKMT_SETDISPLAYMODE, OpenGL_Structs_05a13119-df17-4380-8c9b-8af52c989c73.xml, display.d3dkmt_setdisplaymode, _D3DKMT_SETDISPLAYMODE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_SETDISPLAYMODE
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETDISPLAYMODE
---

# _D3DKMT_SETDISPLAYMODE structure


## -description


The D3DKMT_SETDISPLAYMODE structure describes the primary allocation that is used for scanning out to the display. 


## -syntax


````
typedef struct _D3DKMT_SETDISPLAYMODE {
  D3DKMT_HANDLE                         hDevice;
  D3DKMT_HANDLE                         hPrimaryAllocation;
  D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING ScanLineOrdering;
  D3DDDI_ROTATION                       DisplayOrientation;
  UINT                                  PrivateDriverFormatAttribute;
  D3DKMT_SETDISPLAYMODE_FLAGS           Flags;
} D3DKMT_SETDISPLAYMODE;
````


## -struct-fields




### -field hDevice

[in] A handle to the device that requests setting of the display mode.


### -field hPrimaryAllocation

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the primary allocation for scanning out. 


### -field ScanLineOrdering

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering.md">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field DisplayOrientation

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field PrivateDriverFormatAttribute

[out] A UINT value that specifies a private format attribute that the OpenGL installable client driver (ICD) should use to convert the current primary surface if a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplaymode.md">D3DKMTSetDisplayMode</a> function failed with STATUS_GRAPHICS_INCOMPATIBLE_PRIVATE_FORMAT. 


### -field Flags

Supported in Windows 7 and later versions.

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplaymode_flags.md">D3DKMT_SETDISPLAYMODE_FLAGS</a> structure that specifies, in bit-field flags, attributes for setting the display mode. 


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplaymode_flags.md">D3DKMT_SETDISPLAYMODE_FLAGS</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering.md">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplaymode.md">D3DKMTSetDisplayMode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETDISPLAYMODE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

