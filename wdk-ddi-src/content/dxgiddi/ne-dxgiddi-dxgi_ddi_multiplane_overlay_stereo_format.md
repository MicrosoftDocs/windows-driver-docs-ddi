---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT
title: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT
author: windows-driver-content
description: Identifies the overlay plane's stereo presentation format. Only the DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO value is supported.
old-location: display\dxgi_ddi_multiplane_overlay_stereo_format.htm
old-project: display
ms.assetid: 035edf74-43a0-4de9-805f-c40aba870751
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_ROW_INTERLEAVED, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_CHECKERBOARD, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_COLUMN_INTERLEAVED, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_VERTICAL, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_COLUMN_INTERLEAVED, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_HORIZONTAL, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_VERTICAL, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO_OFFSET, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO_OFFSET, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_SEPARATE, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_HORIZONTAL, display.dxgi_ddi_multiplane_overlay_stereo_format, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO, DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT enumeration [Display Devices], DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_CHECKERBOARD, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_ROW_INTERLEAVED, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_SEPARATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: Dxgiddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dxgiddi.h
apiname:
-	DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT
---

# DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT enumeration


## -description


Identifies the overlay plane's stereo presentation format. Only the <b>DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO</b> value is supported.


## -syntax


````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT { 
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO                = 0,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_HORIZONTAL          = 1,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_VERTICAL            = 2,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_SEPARATE            = 3,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO_OFFSET         = 4,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_ROW_INTERLEAVED     = 5,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_COLUMN_INTERLEAVED  = 6,
  DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_CHECKERBOARD        = 7
} DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT;
````


## -enum-fields




### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO

The overplay plane data is presented in mono (non-stereo) format.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_HORIZONTAL

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_VERTICAL

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_SEPARATE

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO_OFFSET

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_ROW_INTERLEAVED

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_COLUMN_INTERLEAVED

Reserved for system use. Do not use in your driver.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_STEREO_FORMAT_CHECKERBOARD

Reserved for system use. Do not use in your driver.

