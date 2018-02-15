---
UID: NS:dispmprt._DXGK_INTEGRATED_DISPLAY_CHILD
title: "_DXGK_INTEGRATED_DISPLAY_CHILD"
author: windows-driver-content
description: Gives information about the connected integrated display.
old-location: display\dxgk_integrated_display_child.htm
old-project: display
ms.assetid: A3E28664-B286-4E4A-85DD-4EAAC7D257F0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_INTEGRATED_DISPLAY_CHILD, display.dxgk_integrated_display_child, *PDXGK_INTEGRATED_DISPLAY_CHILD, DXGK_INTEGRATED_DISPLAY_CHILD structure [Display Devices], PDXGK_INTEGRATED_DISPLAY_CHILD, _DXGK_INTEGRATED_DISPLAY_CHILD, dispmprt/DXGK_INTEGRATED_DISPLAY_CHILD, dispmprt/PDXGK_INTEGRATED_DISPLAY_CHILD, PDXGK_INTEGRATED_DISPLAY_CHILD structure pointer [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dispmprt.h
apiname:
-	DXGK_INTEGRATED_DISPLAY_CHILD
product: Windows
targetos: Windows
req.typenames: "*PDXGK_INTEGRATED_DISPLAY_CHILD, DXGK_INTEGRATED_DISPLAY_CHILD"
---

# _DXGK_INTEGRATED_DISPLAY_CHILD structure


## -description


Gives information about the connected integrated display.


## -syntax


````
typedef struct _DXGK_INTEGRATED_DISPLAY_CHILD {
  D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY InterfaceTechnology;
  USHORT                          DescriptorLength;
} DXGK_INTEGRATED_DISPLAY_CHILD, *PDXGK_INTEGRATED_DISPLAY_CHILD;
````


## -struct-fields




### -field InterfaceTechnology

Provides the type of connection used for the integrated display.  Typically, this would be one of the inherently internal display types:

<ul>
<li>D3DKMDT_VOT_INTERNAL</li>
<li>D3DKMDT_VOT_LVDS</li>
<li>D3DKMDT_VOT_DISPLAYPORT_EMBEDDED</li>
<li>D3DKMDT_VOT_UDI_EMBEDDED</li>
</ul>
However, since it has become common to use external connector types to connect integrated displays in larger form factor systems with a built-in display such as all-in-one systems, the following digital connection types are also allowed:

<ul>
<li>D3DKMDT_VOT_DVI</li>
<li>D3DKMDT_VOT_HDMI</li>
<li>D3DKMDT_VOT_D_JPN</li>
<li>D3DKMDT_VOT_SDI</li>
<li>D3DKMDT_VOT_DISPLAYPORT_EXTERNAL</li>
<li>D3DKMDT_VOT_UDI_EXTERNAL</li>
</ul>

### -field DescriptorLength

The size in bytes of the descriptor which will be in the Descriptor field of the DXGK_QUERYINTEGRATEDDISPLAYOUT structure.

