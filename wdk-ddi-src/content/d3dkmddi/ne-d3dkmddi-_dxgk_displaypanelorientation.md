---
UID: NE:d3dkmddi._DXGK_DISPLAYPANELORIENTATION
title: "_DXGK_DISPLAYPANELORIENTATION"
author: windows-driver-content
description: Enum used to express the orientation of an integrated panel.
old-location: display\dxgk_displaypanelorientation.htm
old-project: display
ms.assetid: 49758A57-EFCE-4E9C-9BF6-74F6EFD356D9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_DISPLAYPANELORIENTATION, d3dkmddi/DXGK_DPO_180, DXGK_DPO_0, d3dkmddi/DXGK_DPO_270, _DXGK_DISPLAYPANELORIENTATION, DXGK_DPO_90, DXGK_DPO_270, d3dkmddi/DXGK_DPO_90, DXGK_DISPLAYPANELORIENTATION enumeration [Display Devices], DXGK_DPO_180, display.dxgk_displaypanelorientation, d3dkmddi/DXGK_DPO_0, DXGK_DISPLAYPANELORIENTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
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
-	d3dkmddi.h
apiname:
-	DXGK_DISPLAYPANELORIENTATION
product: Windows
targetos: Windows
req.typenames: DXGK_DISPLAYPANELORIENTATION
---

# _DXGK_DISPLAYPANELORIENTATION enumeration


## -description


Enum used to express the orientation of an integrated panel.


## -syntax


````
typedef enum _DXGK_DISPLAYPANELORIENTATION { 
  DXGK_DPO_0    = 0,
  DXGK_DPO_90   = 1,
  DXGK_DPO_180  = 2,
  DXGK_DPO_270  = 3
} DXGK_DISPLAYPANELORIENTATION;
````


## -enum-fields




### -field DXGK_DPO_0

Indicates a 0 degree rotation.


### -field DXGK_DPO_90

Indicates a 90 degree rotation.


### -field DXGK_DPO_180

Indicates a 180 degree rotation.


### -field DXGK_DPO_270

Indicates a 270 degree rotation.


### -field UINT



