---
UID: NE:d3dkmdt._D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
title: _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
author: windows-driver-content
description: The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.
old-location: display\d3dkmdt_video_output_technology.htm
old-project: display
ms.assetid: 5a0876a0-5c27-47aa-9215-1b2bd8612306
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration [Display Devices], d3dkmdt/D3DKMDT_VOT_COMPOSITE_VIDEO, d3dkmdt/D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, d3dkmdt/D3DKMDT_VOT_LVDS, d3dkmdt/D3DKMDT_VOT_SDTVDONGLE, DmEnums_c4d89369-4b10-4033-9bb6-218904fc5c5a.xml, d3dkmdt/D3DKMDT_VOT_RCA_3COMPONENT, d3dkmdt/D3DKMDT_VOT_D_JPN, display.d3dkmdt_video_output_technology, D3DKMDT_VOT_D_JPN, D3DKMDT_VOT_SVIDEO_4PIN, D3DKMDT_VOT_BNC, D3DKMDT_VOT_UDI_EXTERNAL, D3DKMDT_VOT_HDMI, d3dkmdt/D3DKMDT_VOT_SVIDEO_4PIN, D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, d3dkmdt/D3DKMDT_VOT_DISPLAYPORT_EXTERNAL, d3dkmdt/D3DKMDT_VOT_SVIDEO_7PIN, d3dkmdt/D3DKMDT_VOT_INTERNAL, D3DKMDT_VOT_LVDS, D3DKMDT_VOT_SDTVDONGLE, _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY, d3dkmdt/D3DKMDT_VOT_OTHER, D3DKMDT_VOT_DISPLAYPORT_EMBEDDED, d3dkmdt/D3DKMDT_VOT_RF, D3DKMDT_VOT_INTERNAL, d3dkmdt/D3DKMDT_VOT_UDI_EMBEDDED, d3dkmdt/D3DKMDT_VOT_SVIDEO, D3DKMDT_VOT_SVIDEO_7PIN, D3DKMDT_VOT_DVI, d3dkmdt/D3DKMDT_VOT_SDI, D3DKMDT_VOT_MIRACAST, d3dkmdt/D3DKMDT_VOT_HDMI, D3DKMDT_VOT_DISPLAYPORT_EXTERNAL, D3DKMDT_VOT_SVIDEO, d3dkmdt/D3DKMDT_VOT_COMPONENT_VIDEO, D3DKMDT_VOT_COMPONENT_VIDEO, D3DKMDT_VOT_RCA_3COMPONENT, d3dkmdt/D3DKMDT_VOT_UDI_EXTERNAL, d3dkmdt/D3DKMDT_VOT_DVI, d3dkmdt/D3DKMDT_VOT_UNINITIALIZED, D3DKMDT_VOT_RF, d3dkmdt/D3DKMDT_VOT_BNC, D3DKMDT_VOT_UNINITIALIZED, D3DKMDT_VOT_OTHER, D3DKMDT_VOT_HD15, d3dkmdt/D3DKMDT_VOT_DISPLAYPORT_EMBEDDED, d3dkmdt/D3DKMDT_VOT_HD15, d3dkmdt/D3DKMDT_VOT_MIRACAST, D3DKMDT_VOT_SDI, D3DKMDT_VOT_UDI_EMBEDDED, D3DKMDT_VOT_COMPOSITE_VIDEO
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmdt.h
apiname: 
-	D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
---

# _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration


## -description


The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.


## -syntax


````
typedef enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY { 
  D3DKMDT_VOT_UNINITIALIZED         = -2,
  D3DKMDT_VOT_OTHER                 = -1,
  D3DKMDT_VOT_HD15                  = 0,
  D3DKMDT_VOT_SVIDEO                = 1,
  D3DKMDT_VOT_COMPOSITE_VIDEO       = 2,
  D3DKMDT_VOT_COMPONENT_VIDEO       = 3,
  D3DKMDT_VOT_DVI                   = 4,
  D3DKMDT_VOT_HDMI                  = 5,
  D3DKMDT_VOT_LVDS                  = 6,
  D3DKMDT_VOT_D_JPN                 = 8,
  D3DKMDT_VOT_SDI                   = 9,
  D3DKMDT_VOT_DISPLAYPORT_EXTERNAL  = 10,
  D3DKMDT_VOT_DISPLAYPORT_EMBEDDED  = 11,
  D3DKMDT_VOT_UDI_EXTERNAL          = 12,
  D3DKMDT_VOT_UDI_EMBEDDED          = 13,
  D3DKMDT_VOT_SDTVDONGLE            = 14,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
  D3DKMDT_VOT_MIRACAST              = 15,
#endif 
  D3DKMDT_VOT_INTERNAL              = 0x80000000,
  D3DKMDT_VOT_SVIDEO_4PIN           = D3DKMDT_VOT_SVIDEO,
  D3DKMDT_VOT_SVIDEO_7PIN           = D3DKMDT_VOT_SVIDEO,
  D3DKMDT_VOT_RF                    = D3DKMDT_VOT_COMPOSITE_VIDEO,
  D3DKMDT_VOT_RCA_3COMPONENT        = D3DKMDT_VOT_COMPONENT_VIDEO,
  D3DKMDT_VOT_BNC                   = D3DKMDT_VOT_COMPONENT_VIDEO
} D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY;
````


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


The <b>ChildCapabilities</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_capabilities.md">DXGK_CHILD_CAPABILITIES</a> structure. The <b>Type.VideoOutput</b> member of a DXGK_CHILD_CAPABILITIES structure is a <a href="..\dispmprt\ns-dispmprt-_dxgk_video_output_capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure. The <b>InterfaceTechnology</b> member of a DXGK_VIDEO_OUTPUT_CAPABILITIES structure is a D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY value.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>

<a href="..\dispmprt\ns-dispmprt-_dxgk_video_output_capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

