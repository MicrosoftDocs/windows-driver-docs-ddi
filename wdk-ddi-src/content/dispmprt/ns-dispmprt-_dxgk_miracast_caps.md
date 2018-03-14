---
UID: NS:dispmprt._DXGK_MIRACAST_CAPS
title: "_DXGK_MIRACAST_CAPS"
author: windows-driver-content
description: Used by a display miniport driver to identify capabilities of a Miracast device.
old-location: display\dxgk_miracast_caps.htm
old-project: display
ms.assetid: 63ED28D9-654F-45CC-BFDC-89C9E73DCF95
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_MIRACAST_CAPS, DXGK_MIRACAST_CAPS, DXGK_MIRACAST_CAPS structure [Display Devices], PDXGK_MIRACAST_CAPS, PDXGK_MIRACAST_CAPS structure pointer [Display Devices], _DXGK_MIRACAST_CAPS, display.dxgk_miracast_caps, dispmprt/DXGK_MIRACAST_CAPS, dispmprt/PDXGK_MIRACAST_CAPS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_MIRACAST_CAPS
product: Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_CAPS, *PDXGK_MIRACAST_CAPS
---

# _DXGK_MIRACAST_CAPS structure


## -description


Used by a display miniport driver to identify capabilities of a Miracast device.


## -syntax


````
typedef struct _DXGK_MIRACAST_CAPS {
  ULONG MaxChunkPrivateDriverDataSize;
  union {
    struct {
      UINT HdcpSupport  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  } Flags;
} DXGK_MIRACAST_CAPS, *PDXGK_MIRACAST_CAPS;
````


## -struct-fields




### -field MaxChunkPrivateDriverDataSize

The maximum size, in bytes, of the private data that the display miniport driver will pass when it reports a <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a> interrupt type of <b>DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE</b>.


### -field Flags



#### Value

Holds a 32-bit value that identifies the capabilities of the Miracast device.


### -field Flags.HdcpSupport

Indicates whether the display adapter supports the Miracast High-bandwidth Digital Content Protection (HDCP) feature.


### -field Flags.Reserved

Reserved for system use. The display miniport driver must set this value to zero.


## -see-also

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>



 

 


