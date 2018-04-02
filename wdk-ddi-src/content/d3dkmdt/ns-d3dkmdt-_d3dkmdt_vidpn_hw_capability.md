---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_HW_CAPABILITY
title: "_D3DKMDT_VIDPN_HW_CAPABILITY"
author: windows-driver-content
description: The D3DKMDT_VIDPN_HW_CAPABILITY structure describes the capabilities of the display miniport driver to perform display operations on a specified functional VidPN without dedicated GPU hardware support.
old-location: display\d3dkmdt_vidpn_hw_capability.htm
old-project: display
ms.assetid: 8d881133-3ea7-43c4-99cc-d843026573d6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VIDPN_HW_CAPABILITY, D3DKMDT_VIDPN_HW_CAPABILITY structure [Display Devices], DmStructs_93529025-7af3-49d1-8f38-2b0355682743.xml, _D3DKMDT_VIDPN_HW_CAPABILITY, d3dkmdt/D3DKMDT_VIDPN_HW_CAPABILITY, display.d3dkmdt_vidpn_hw_capability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDPN_HW_CAPABILITY
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_HW_CAPABILITY
---

# _D3DKMDT_VIDPN_HW_CAPABILITY structure


## -description


The D3DKMDT_VIDPN_HW_CAPABILITY structure describes the capabilities of the display miniport driver to perform display operations on a specified functional VidPN without dedicated GPU hardware support. For definitions of hardware terminology used in this topic, see the Remarks section.


## -struct-fields




### -field DriverRotation

A UINT value that describes the capability of the display miniport driver to display a rotated image.

If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the rotated image and then uses display pipeline hardware to display the rotated image.

If set to 0, the driver uses display pipeline hardware to directly generate the rotated image.


### -field DriverScaling

A UINT value that describes the capability of the display miniport driver to display a scaled image.

If set to a nonzero value, the driver uses software or the system-supplied graphics engine to scale the on-screen image and then uses display pipeline hardware to display the scaled image.

If set to 0, the driver uses display pipeline hardware to directly generate the scaled image.


### -field DriverCloning

A UINT value that describes the capability of the display miniport driver to display a cloned image.

If set to a nonzero value, the driver uses software or the system-supplied graphics engine to copy the on-screen image and then uses display pipeline hardware to display the copy.

If set to 0, the driver uses display pipeline hardware to directly generate the cloned image.


### -field DriverColorConvert

A UINT value that describes the capability of the display miniport driver to display a color-convert bit-block transfer (bitblt).

If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the color-convert bitblt and then uses display pipeline hardware to display the color-converted image. For example, if the display pipeline hardware cannot color-convert from an 8-bit palletized surface format (defined by the D3DDDIFMT_P8 value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration), the driver can use the graphics engine to perform a color-convert bitblt from the D3DDDIFMT_ P8 format to the D3DDDIFMT_R8G8B8 format and then render the new D3DDDIFMT_R8G8B8 image using the display pipeline hardware.

If set to 0, the driver uses display pipeline hardware to directly generate the color-converted image.


### -field DriverLinkedAdapaterOutput

A UINT value that describes the capability of the display miniport driver to perform a bit-block transfer (bitblt) of a primary surface from one linked display adapter to another linked display adapter.

If set to a nonzero value, the driver uses software or the system-supplied graphics engine to generate the bitblt from the on-screen image on the first linked display adapter and then uses the second linked display adapter to display the bitblt image on the second display device.

If set to 0, the driver uses display pipeline hardware to directly generate the bitblt from the first linked display adapter and to display it with the second linked display adapter.


### -field DriverRemoteDisplay

A UINT value that describes whether the display pipeline hardware is located on the same device as the GPU graphics rendering pipeline.

If set to a nonzero value, the display pipeline hardware is not located on the same device as the GPU graphics rendering pipeline, and the primary surface might have to be transmitted over a bus that is not designed specifically for display image transfers. Examples of such remote display situations are a display monitor that is connected to the computer with a USB bus and a display that is connected remotely over a network.

If set to 0, the display pipeline hardware is located on the same device as the GPU graphics rendering pipeline.


### -field Reserved

Reserved for system use. The display miniport driver must set this value to 0.


## -remarks



The following definitions of terms are used in this topic.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>
 

 

