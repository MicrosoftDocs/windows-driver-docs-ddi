---
UID: NE:dxgiddi.DXGI_DDI_FLIP_INTERVAL_TYPE
title: DXGI_DDI_FLIP_INTERVAL_TYPE
author: windows-driver-content
description: The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\dxgi_ddi_flip_interval_type.htm
old-project: display
ms.assetid: e33da768-9d57-4b07-9c4e-c86d19828291
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_FLIP_INTERVAL_ONE, DXGI_DDI_FLIP_INTERVAL_TWO, dxgiddi/DXGI_DDI_FLIP_INTERVAL_THREE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_IMMEDIATE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_FOUR, DXGI_DDI_FLIP_INTERVAL_TYPE, DXGI_DDI_FLIP_INTERVAL_THREE, DXGI_DDI_FLIP_INTERVAL_IMMEDIATE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_TWO, UMDisplayDriver_Dx10param_Structs_65a96d1c-4c37-4fdd-b79e-2a90559db67d.xml, display.dxgi_ddi_flip_interval_type, dxgiddi/DXGI_DDI_FLIP_INTERVAL_ONE, dxgiddi/DXGI_DDI_FLIP_INTERVAL_TYPE, DXGI_DDI_FLIP_INTERVAL_TYPE enumeration [Display Devices], DXGI_DDI_FLIP_INTERVAL_FOUR
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
-	DXGI_DDI_FLIP_INTERVAL_TYPE
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_FLIP_INTERVAL_TYPE
---

# DXGI_DDI_FLIP_INTERVAL_TYPE enumeration


## -description


The DXGI_DDI_FLIP_INTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.


## -syntax


````
typedef enum DXGI_DDI_FLIP_INTERVAL_TYPE { 
  DXGI_DDI_FLIP_INTERVAL_IMMEDIATE  = 0,
  DXGI_DDI_FLIP_INTERVAL_ONE        = 1,
  DXGI_DDI_FLIP_INTERVAL_TWO        = 2,
  DXGI_DDI_FLIP_INTERVAL_THREE      = 3,
  DXGI_DDI_FLIP_INTERVAL_FOUR       = 4
} DXGI_DDI_FLIP_INTERVAL_TYPE;
````


## -enum-fields




### -field DXGI_DDI_FLIP_INTERVAL_IMMEDIATE

Indicates to perform the flip immediately without waiting for a vertical sync to occur. 


### -field DXGI_DDI_FLIP_INTERVAL_ONE

Indicates to perform the flip on every vertical sync. 


### -field DXGI_DDI_FLIP_INTERVAL_TWO

Indicates to perform the flip on every other vertical sync. 


### -field DXGI_DDI_FLIP_INTERVAL_THREE

Indicates to perform the flip on every third vertical sync.


### -field DXGI_DDI_FLIP_INTERVAL_FOUR

Indicates to perform the flip on every fourth vertical sync.


### -field DXGI_DDI_FLIP_INTERVAL_IMMEDIATE_ALLOW_TEARING




## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_FLIP_INTERVAL_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

