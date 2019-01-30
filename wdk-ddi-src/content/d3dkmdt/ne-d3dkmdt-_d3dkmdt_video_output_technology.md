---
UID: NE:d3dkmdt._D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
title: _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY (d3dkmdt.h)
description: The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.
old-location: display\d3dkmdt_video_output_technology.htm
tech.root: display
ms.assetid: 5a0876a0-5c27-47aa-9215-1b2bd8612306
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration [Display Devices], D3DKMDT_VOT_BNC, D3DKMDT_VOT_COMPONENT_VIDEO, D3DKMDT_VOT_COMPOSITE_VIDEO, D3DKMDT_VOT_DISPLAYPORT_EMBEDDED, D3DKMDT_VOT_DISPLAYPORT_EXTERNAL, D3DKMDT_VOT_DVI, D3DKMDT_VOT_D_JPN, D3DKMDT_VOT_HD15, D3DKMDT_VOT_HDMI, D3DKMDT_VOT_INTERNAL, D3DKMDT_VOT_LVDS, D3DKMDT_VOT_MIRACAST, D3DKMDT_VOT_OTHER, D3DKMDT_VOT_RCA_3COMPONENT, D3DKMDT_VOT_RF, D3DKMDT_VOT_SDI, D3DKMDT_VOT_SDTVDONGLE, D3DKMDT_VOT_SVIDEO, D3DKMDT_VOT_SVIDEO_4PIN, D3DKMDT_VOT_SVIDEO_7PIN, D3DKMDT_VOT_UDI_EMBEDDED, D3DKMDT_VOT_UDI_EXTERNAL, D3DKMDT_VOT_UNINITIALIZED, DmEnums_c4d89369-4b10-4033-9bb6-218904fc5c5a.xml, _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, d3dkmdt/D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, d3dkmdt/D3DKMDT_VOT_BNC, d3dkmdt/D3DKMDT_VOT_COMPONENT_VIDEO, d3dkmdt/D3DKMDT_VOT_COMPOSITE_VIDEO, d3dkmdt/D3DKMDT_VOT_DISPLAYPORT_EMBEDDED, d3dkmdt/D3DKMDT_VOT_DISPLAYPORT_EXTERNAL, d3dkmdt/D3DKMDT_VOT_DVI, d3dkmdt/D3DKMDT_VOT_D_JPN, d3dkmdt/D3DKMDT_VOT_HD15, d3dkmdt/D3DKMDT_VOT_HDMI, d3dkmdt/D3DKMDT_VOT_INTERNAL, d3dkmdt/D3DKMDT_VOT_LVDS, d3dkmdt/D3DKMDT_VOT_MIRACAST, d3dkmdt/D3DKMDT_VOT_OTHER, d3dkmdt/D3DKMDT_VOT_RCA_3COMPONENT, d3dkmdt/D3DKMDT_VOT_RF, d3dkmdt/D3DKMDT_VOT_SDI, d3dkmdt/D3DKMDT_VOT_SDTVDONGLE, d3dkmdt/D3DKMDT_VOT_SVIDEO, d3dkmdt/D3DKMDT_VOT_SVIDEO_4PIN, d3dkmdt/D3DKMDT_VOT_SVIDEO_7PIN, d3dkmdt/D3DKMDT_VOT_UDI_EMBEDDED, d3dkmdt/D3DKMDT_VOT_UDI_EXTERNAL, d3dkmdt/D3DKMDT_VOT_UNINITIALIZED, display.d3dkmdt_video_output_technology
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
---

# _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration


## -description


The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.


## -enum-fields




### -field D3DKMDT_VOT_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY has not yet been assigned a meaningful value.


### -field D3DKMDT_VOT_OTHER

Indicates that the video output device connects to an external display device through a connector that is not one of the types that is indicated by the following values in this enumeration.


### -field D3DKMDT_VOT_HD15

Indicates that the video output device connects to an external display device through an HD15 (VGA) connector.


### -field D3DKMDT_VOT_SVIDEO

Indicates that the video output device connects to an external display device through an S-video connector.


### -field D3DKMDT_VOT_COMPOSITE_VIDEO

Indicates that the video output device connects to an external display device through composite video connectors.


### -field D3DKMDT_VOT_COMPONENT_VIDEO

Indicates that the video output device connects to an external display device through component video connectors.


### -field D3DKMDT_VOT_DVI

Indicates that the video output device connects to an external display device through a Digital Video Interface (DVI) connector.


### -field D3DKMDT_VOT_HDMI

Indicates that the video output device connects to an external display device through an High-Definition Multimedia Interface (HDMI) connector.


### -field D3DKMDT_VOT_LVDS

Indicates that the video output device connects to an external display device through an Low Voltage Differential Swing (LVDS) or Mobile Industry Processor Interface (MIPI) Digital Serial Interface (DSI) connector.


### -field D3DKMDT_VOT_D_JPN

Indicates that the video output device connects to an external display device through a D-Jpn connector. 


### -field D3DKMDT_VOT_SDI

Indicates that the video output device connects to an external display device through an SDI connector. 


### -field D3DKMDT_VOT_DISPLAYPORT_EXTERNAL

Indicates that the connector type is an external display port. 


### -field D3DKMDT_VOT_DISPLAYPORT_EMBEDDED

Indicates that the connector type is an embedded display port. 


### -field D3DKMDT_VOT_UDI_EXTERNAL

Indicates that the connector type is an external Unified Display Interface (UDI). 


### -field D3DKMDT_VOT_UDI_EMBEDDED

Indicates that the connector type is an embedded UDI. 


### -field D3DKMDT_VOT_SDTVDONGLE

Indicates that the video output device connects to an external display device through a dongle cable that supports SDTV. 


### -field D3DKMDT_VOT_MIRACAST

Indicates that the video output device connects to an external display device wirelessly through a Miracast connected session. For more info, see <a href="https://msdn.microsoft.com/1645E14A-EC4A-4EB8-9AFA-6DF0466D2B1A">Wireless displays (Miracast)</a>.

Supported starting with Windows 8.1.


### -field D3DKMDT_VOT_INDIRECT_WIRED


### -field D3DKMDT_VOT_INTERNAL

Indicates that the video output device connects internally to a display device (for example, the internal connection in a laptop computer).

This constant value is not a bit-field value. Instead, it's a standalone video output type.


### -field D3DKMDT_VOT_SVIDEO_4PIN

Indicates that the video output device connects to an external display device through a 4-pin S-video connector.


### -field D3DKMDT_VOT_SVIDEO_7PIN

Indicates that the video output device connects to an external display device through a 7-pin S-video connector.


### -field D3DKMDT_VOT_RF

Indicates that the video output device connects to an external display device through an RF connector.


### -field D3DKMDT_VOT_RCA_3COMPONENT

Indicates that the video output device connects to an external display device through a set of three RCA connectors.


### -field D3DKMDT_VOT_BNC

Indicates that the video output device connects to an external display device through a BNC connector.


## -remarks



The <b>ChildCapabilities</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560995">DXGK_CHILD_CAPABILITIES</a> structure. The <b>Type.VideoOutput</b> member of a DXGK_CHILD_CAPABILITIES structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562070">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure. The <b>InterfaceTechnology</b> member of a DXGK_VIDEO_OUTPUT_CAPABILITIES structure is a D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562070">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>
 

 

