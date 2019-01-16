---
UID: NE:d3dkmddi._DXGK_VIDPN_INTERFACE_VERSION
title: "_DXGK_VIDPN_INTERFACE_VERSION"
description: The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface.
old-location: display\dxgk_vidpn_interface_version.htm
ms.assetid: 819261a5-bec0-49a8-942a-9313d3b793ca
ms.date: 05/10/2018
ms.keywords: DXGK_VIDPN_INTERFACE_VERSION, DXGK_VIDPN_INTERFACE_VERSION enumeration [Display Devices], DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, DXGK_VIDPN_INTERFACE_VERSION_V1, DmEnums_69c4e28b-70fe-4576-b726-6fa6d78c97d0.xml, _DXGK_VIDPN_INTERFACE_VERSION, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_V1, display.dxgk_vidpn_interface_version
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_VIDPN_INTERFACE_VERSION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_VIDPN_INTERFACE_VERSION
---

# _DXGK_VIDPN_INTERFACE_VERSION enumeration


## -description


The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface.


## -enum-fields




### -field DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED

Indicates that a variable of type DXGK_VIDPN_INTERFACE_VERSION has not yet been assigned a meaningful value.


### -field DXGK_VIDPN_INTERFACE_VERSION_V1

Indicates version 1 of the VidPN interface.


## -remarks



The <i>VidPnInterfaceVersion</i> parameter of the <a href="https://msdn.microsoft.com/649ce7fc-6852-43f3-b944-b2b64fcba874">DxgkCbQueryVidPnInterface</a> function and the <b>Version</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> structure are DXGK_VIDPN_INTERFACE_VERSION values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn Interface</a>
 

 

