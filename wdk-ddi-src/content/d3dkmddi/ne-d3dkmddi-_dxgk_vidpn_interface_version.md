---
UID: NE:d3dkmddi._DXGK_VIDPN_INTERFACE_VERSION
title: _DXGK_VIDPN_INTERFACE_VERSION
author: windows-driver-content
description: The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface.
old-location: display\dxgk_vidpn_interface_version.htm
old-project: display
ms.assetid: 819261a5-bec0-49a8-942a-9313d3b793ca
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, DXGK_VIDPN_INTERFACE_VERSION, DXGK_VIDPN_INTERFACE_VERSION enumeration [Display Devices], _DXGK_VIDPN_INTERFACE_VERSION, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, DmEnums_69c4e28b-70fe-4576-b726-6fa6d78c97d0.xml, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION, display.dxgk_vidpn_interface_version, DXGK_VIDPN_INTERFACE_VERSION_V1, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_V1
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_VIDPN_INTERFACE_VERSION
product: Windows
targetos: Windows
req.typenames: DXGK_VIDPN_INTERFACE_VERSION
---

# _DXGK_VIDPN_INTERFACE_VERSION enumeration


## -description


The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface.


## -syntax


````
typedef enum _DXGK_VIDPN_INTERFACE_VERSION { 
  DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED  = 0,
  DXGK_VIDPN_INTERFACE_VERSION_V1             = 1
} DXGK_VIDPN_INTERFACE_VERSION;
````


## -enum-fields




### -field DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED

Indicates that a variable of type DXGK_VIDPN_INTERFACE_VERSION has not yet been assigned a meaningful value.


### -field DXGK_VIDPN_INTERFACE_VERSION_V1

Indicates version 1 of the VidPN interface.


## -remarks


The <i>VidPnInterfaceVersion</i> parameter of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_queryvidpninterface.md">DxgkCbQueryVidPnInterface</a> function and the <b>Version</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> structure are DXGK_VIDPN_INTERFACE_VERSION values.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570556">VidPn Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_VIDPN_INTERFACE_VERSION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

