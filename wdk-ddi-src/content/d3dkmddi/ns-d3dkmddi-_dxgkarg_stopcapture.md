---
UID: NS:d3dkmddi._DXGKARG_STOPCAPTURE
title: "_DXGKARG_STOPCAPTURE"
author: windows-driver-content
description: The DXGKARG_STOPCAPTURE structure contains the handle to the allocation that is used for a capture buffer.
old-location: display\dxgkarg_stopcapture.htm
old-project: display
ms.assetid: 09b1275f-9755-44f7-ab8a-1b6797bfefde
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_STOPCAPTURE, DXGKARG_STOPCAPTURE structure [Display Devices], DmStructs_52028d90-8c11-425c-80ca-533664035fa5.xml, _DXGKARG_STOPCAPTURE, d3dkmddi/DXGKARG_STOPCAPTURE, display.dxgkarg_stopcapture
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_STOPCAPTURE
product: Windows
targetos: Windows
req.typenames: DXGKARG_STOPCAPTURE
---

# _DXGKARG_STOPCAPTURE structure


## -description


The DXGKARG_STOPCAPTURE structure contains the handle to the allocation that is used for a capture buffer.


## -syntax


````
typedef struct _DXGKARG_STOPCAPTURE {
  HANDLE hAllocation;
} DXGKARG_STOPCAPTURE;
````


## -struct-fields




### -field hAllocation

[in] A handle to the allocation that is used for a capture buffer. The display miniport driver stops the capture hardware from using the allocation.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_stopcapture.md">DxgkDdiStopCapture</a>



 

 


