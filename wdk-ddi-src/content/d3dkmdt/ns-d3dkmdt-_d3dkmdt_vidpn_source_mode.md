---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_SOURCE_MODE
title: "_D3DKMDT_VIDPN_SOURCE_MODE"
author: windows-driver-content
description: The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.
old-location: display\d3dkmdt_vidpn_source_mode.htm
old-project: display
ms.assetid: 763db6bb-8991-406d-a1d4-8ad50e32fee1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_VIDPN_SOURCE_MODE, D3DKMDT_VIDPN_SOURCE_MODE structure [Display Devices], DmStructs_0e8655c2-a85f-411d-a791-4c85e5c7d52c.xml, _D3DKMDT_VIDPN_SOURCE_MODE, d3dkmdt/D3DKMDT_VIDPN_SOURCE_MODE, display.d3dkmdt_vidpn_source_mode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DKMDT_VIDPN_SOURCE_MODE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_SOURCE_MODE
---

# _D3DKMDT_VIDPN_SOURCE_MODE structure


## -description


The D3DKMDT_VIDPN_SOURCE_MODE structure contains information about a video present network (VidPN) source mode.


## -syntax


````
typedef struct _D3DKMDT_VIDPN_SOURCE_MODE {
  D3DKMDT_VIDEO_PRESENT_SOURCE_MODE_ID Id;
  D3DKMDT_VIDPN_SOURCE_MODE_TYPE       Type;
  union {
    D3DKMDT_GRAPHICS_RENDERING_FORMAT Graphics;
    D3DKMDT_TEXT_RENDERING_FORMAT     Text;
  } Format;
} D3DKMDT_VIDPN_SOURCE_MODE;
````


## -struct-fields




### -field Id

An integer that identifies the source mode. The identifier is generated and filled in by the VidPN manager. However, the display miniport driver has the option of overwriting the identifier. For more information, see <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpnsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.


### -field Type

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_source_mode_type.md">D3DKMDT_VIDPN_SOURCE_MODE_TYPE</a> enumerator that indicates the mode type: graphics or text.


### -field Format

A union that contains information about either the graphics rendering format or the text format in the following members. 




#### Graphics

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_graphics_rendering_format.md">D3DKMDT_GRAPHICS_RENDERING_FORMAT</a> structure that contains information about the graphics rendering format (for example, primary surface size and pixel format). This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_GRAPHICS.



#### Text

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_text_rendering_format.md">D3DKMDT_TEXT_RENDERING_FORMAT</a> enumerator that indicates the text format. This member is meaningful only if the <b>Type</b> member is equal to D3DKMDT_RMT_TEXT.


## -remarks



For more information about video present sources and VidPN source modes, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a> and <a href="https://msdn.microsoft.com/f1aa6277-7af6-4ba0-8ff1-d562f7029540">Enumerating Cofunctional VidPN Source and Target Modes</a>.




## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570558">VidPN Source Mode Set Interface</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a>



 

 


