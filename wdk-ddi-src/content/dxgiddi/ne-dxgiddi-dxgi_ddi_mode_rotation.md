---
UID: NE:dxgiddi.DXGI_DDI_MODE_ROTATION
title: DXGI_DDI_MODE_ROTATION
author: windows-driver-content
description: The DXGI_DDI_MODE_ROTATION enumeration type contains values that identify the orientation of the display.
old-location: display\dxgi_ddi_mode_rotation.htm
old-project: display
ms.assetid: 8cc413c4-e4fe-449b-a66a-c79da01ad3be
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: dxgiddi/DXGI_DDI_MODE_ROTATION_UNSPECIFIED, dxgiddi/DXGI_DDI_MODE_ROTATION_ROTATE270, DXGI_DDI_MODE_ROTATION_UNSPECIFIED, dxgiddi/DXGI_DDI_MODE_ROTATION, DXGI_DDI_MODE_ROTATION_ROTATE270, DXGI_DDI_MODE_ROTATION enumeration [Display Devices], DXGI_DDI_MODE_ROTATION_ROTATE90, dxgiddi/DXGI_DDI_MODE_ROTATION_IDENTITY, dxgiddi/DXGI_DDI_MODE_ROTATION_ROTATE90, UMDisplayDriver_Dx10param_Structs_61b842eb-a4b4-4d86-95b8-eca448b35b5e.xml, DXGI_DDI_MODE_ROTATION, DXGI_DDI_MODE_ROTATION_ROTATE180, dxgiddi/DXGI_DDI_MODE_ROTATION_ROTATE180, DXGI_DDI_MODE_ROTATION_IDENTITY, display.dxgi_ddi_mode_rotation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
-	dxgiddi.h
apiname:
-	DXGI_DDI_MODE_ROTATION
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_ROTATION
---

# DXGI_DDI_MODE_ROTATION enumeration


## -description


The DXGI_DDI_MODE_ROTATION enumeration type contains values that identify the orientation of the display.


## -syntax


````
typedef enum DXGI_DDI_MODE_ROTATION { 
  DXGI_DDI_MODE_ROTATION_UNSPECIFIED  = 0,
  DXGI_DDI_MODE_ROTATION_IDENTITY     = 1,
  DXGI_DDI_MODE_ROTATION_ROTATE90     = 2,
  DXGI_DDI_MODE_ROTATION_ROTATE180    = 3,
  DXGI_DDI_MODE_ROTATION_ROTATE270    = 4
} DXGI_DDI_MODE_ROTATION;
````


## -enum-fields




### -field DXGI_DDI_MODE_ROTATION_UNSPECIFIED

A DXGI_DDI_MODE_ROTATION-typed variable has not yet been assigned a meaningful value.


### -field DXGI_DDI_MODE_ROTATION_IDENTITY

The display is not rotated.


### -field DXGI_DDI_MODE_ROTATION_ROTATE90

The display is rotated 90 degrees.


### -field DXGI_DDI_MODE_ROTATION_ROTATE180

The display is rotated 180 degrees.


### -field DXGI_DDI_MODE_ROTATION_ROTATE270

The display is rotated 270 degrees.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_MODE_ROTATION enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

