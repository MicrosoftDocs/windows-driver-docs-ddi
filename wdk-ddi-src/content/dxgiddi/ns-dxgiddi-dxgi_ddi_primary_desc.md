---
UID: NS:dxgiddi.DXGI_DDI_PRIMARY_DESC
title: DXGI_DDI_PRIMARY_DESC
author: windows-driver-content
description: Describes a resource that is used as a primary (that is, a resource that is scanned out to the display).
old-location: display\dxgi_ddi_primary_desc.htm
old-project: display
ms.assetid: eb6db822-c6d3-43d0-91af-49d19189ed83
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_PRIMARY_DESC, DXGI_DDI_PRIMARY_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_PRIMARY_DESC
req.alt-loc: dxgiddi.h
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
req.typenames: DXGI_DDI_PRIMARY_DESC
---

# DXGI_DDI_PRIMARY_DESC structure



## -description
Describes a resource that is used as a primary (that is, a resource that is scanned out to the display). 



## -syntax

````
typedef struct DXGI_DDI_PRIMARY_DESC {
  UINT                           Flags;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  DXGI_DDI_MODE_DESC             ModeDesc;
  UINT                           DriverFlags;
} DXGI_DDI_PRIMARY_DESC;
````


## -struct-fields

### -field Flags

[in] A valid bitwise OR of any of the following values that indicates how the resource is displayed. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DXGI_DDI_PRIMARY_OPTIONAL (0x1)

</td>
<td>
The user-mode display driver can prevent the resource from ever being a primary. 

The driver can prevent the actual flip (from optional primary to regular primary) and can use a copy-style present operation. Therefore, in this way, the driver might be able to prevent the resource from being actually used as a primary.

</td>
</tr>
<tr>
<td>
DXGI_DDI_PRIMARY_NONPREROTATED (0x2)

</td>
<td>
The primary really represents the DXGI_DDI_MODE_ROTATION_IDENTITY-type rotation, even though it is used with non-DXGI_DDI_MODE_ROTATION_IDENTITY-type display modes, because applications will handle the output orientation by rotating, for example, the viewport and projection matrix.

</td>
</tr>
<tr>
<td>
DXGI_DDI_PRIMARY_STEREO (0x4)

</td>
<td>
Supported in   Windows 8 and later versions.

The primary represents a stereo back buffer.

</td>
</tr>
</table>
 


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the primary surface is created on. 


### -field ModeDesc

[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a> structure that describes the display mode. 


### -field DriverFlags

[out] A valid bitwise OR of values that indicate how the driver can display the resource. 

The DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT (0x1) value is currently the only supported value. This bit indicates that the driver cannot support the runtime setting any subresource of the specified resource as a primary. The user-mode display driver should set this bit if it implements presentation from this surface through a copy operation. Therefore, the runtime will not use flip-style presentation if this bit is set. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_PRIMARY_DESC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

