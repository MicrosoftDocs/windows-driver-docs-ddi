---
UID: NE:dxgiddi.DXGI_DDI_MODE_SCALING
title: DXGI_DDI_MODE_SCALING
author: windows-driver-content
description: The DXGI_DDI_MODE_SCALING enumeration type contains values that identify the scaling support for a display.
old-location: display\dxgi_ddi_mode_scaling.htm
old-project: display
ms.assetid: dfe37343-18a6-46f2-b23f-52fc0ca2f800
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_Dx10param_Structs_fce25008-9fff-4a5a-9bdc-2e9a6055ef06.xml, dxgiddi/DXGI_DDI_MODE_SCALING_STRETCHED, display.dxgi_ddi_mode_scaling, DXGI_DDI_MODE_SCALING_STRETCHED, DXGI_DDI_MODE_SCALING_CENTERED, dxgiddi/DXGI_DDI_MODE_SCALING, DXGI_DDI_MODE_SCALING, dxgiddi/DXGI_DDI_MODE_SCALING_CENTERED, dxgiddi/DXGI_DDI_MODE_SCALING_UNSPECIFIED, DXGI_DDI_MODE_SCALING enumeration [Display Devices], DXGI_DDI_MODE_SCALING_UNSPECIFIED
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
-	DXGI_DDI_MODE_SCALING
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_SCALING
---

# DXGI_DDI_MODE_SCALING enumeration


## -description


The DXGI_DDI_MODE_SCALING enumeration type contains values that identify the scaling support for a display.


## -syntax


````
typedef enum DXGI_DDI_MODE_SCALING { 
  DXGI_DDI_MODE_SCALING_UNSPECIFIED  = 0,
  DXGI_DDI_MODE_SCALING_STRETCHED    = 1,
  DXGI_DDI_MODE_SCALING_CENTERED     = 2
} DXGI_DDI_MODE_SCALING;
````


## -enum-fields




### -field DXGI_DDI_MODE_SCALING_UNSPECIFIED

A DXGI_DDI_MODE_SCALING-typed variable has not yet been assigned a meaningful value.


### -field DXGI_DDI_MODE_SCALING_STRETCHED

Stretched content can be displayed. 


### -field DXGI_DDI_MODE_SCALING_CENTERED

Centered content can be displayed. 


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_MODE_SCALING enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

