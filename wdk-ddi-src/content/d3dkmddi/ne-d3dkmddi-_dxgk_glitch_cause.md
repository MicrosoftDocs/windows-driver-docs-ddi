---
UID: NE:d3dkmddi._DXGK_GLITCH_CAUSE
title: "_DXGK_GLITCH_CAUSE"
author: windows-driver-content
description: Enumeration that describes what caused a glitch during a SetTimingsFromVidPn call.
old-location: display\dxgk_glitch_cause.htm
old-project: display
ms.assetid: A0356AE8-3A82-4722-9F46-8FE05646BF10
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGK_GLITCH_CAUSE, DXGK_GLITCH_CAUSE enumeration [Display Devices], DXGK_GLITCH_CAUSE_DRIVER_ERROR, DXGK_GLITCH_CAUSE_ENCODER_RECONFIG, DXGK_GLITCH_CAUSE_MEMORY_TIMING, DXGK_GLITCH_CAUSE_METADATA_CHANGE, DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE, DXGK_GLITCH_CAUSE_NONE, DXGK_GLITCH_CAUSE_PIPELINE_CHANGE, DXGK_GLITCH_CAUSE_TIMING_CHANGE, E, G, H, I, K, L, S, T, U, X, _, _DXGK_GLITCH_CAUSE, d3dkmddi/DXGK_GLITCH_CAUSE, d3dkmddi/DXGK_GLITCH_CAUSE_DRIVER_ERROR, d3dkmddi/DXGK_GLITCH_CAUSE_ENCODER_RECONFIG, d3dkmddi/DXGK_GLITCH_CAUSE_MEMORY_TIMING, d3dkmddi/DXGK_GLITCH_CAUSE_METADATA_CHANGE, d3dkmddi/DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE, d3dkmddi/DXGK_GLITCH_CAUSE_NONE, d3dkmddi/DXGK_GLITCH_CAUSE_PIPELINE_CHANGE, d3dkmddi/DXGK_GLITCH_CAUSE_TIMING_CHANGE, display.dxgk_glitch_cause"
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
-	DXGK_GLITCH_CAUSE
product: Windows
targetos: Windows
req.typenames: DXGK_GLITCH_CAUSE
---

# _DXGK_GLITCH_CAUSE enumeration


## -description


Enumeration that describes what caused a glitch during a SetTimingsFromVidPn call.


## -syntax


````
typedef enum _DXGK_GLITCH_CAUSE { 
  DXGK_GLITCH_CAUSE_DRIVER_ERROR         = 0,
  DXGK_GLITCH_CAUSE_TIMING_CHANGE        = 1,
  DXGK_GLITCH_CAUSE_PIPELINE_CHANGE      = 2,
  DXGK_GLITCH_CAUSE_MEMORY_TIMING        = 3,
  DXGK_GLITCH_CAUSE_ENCODER_RECONFIG     = 4,
  DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE  = 5,
  DXGK_GLITCH_CAUSE_METADATA_CHANGE      = 6,
  DXGK_GLITCH_CAUSE_NONE                 = 255
} DXGK_GLITCH_CAUSE;
````


## -enum-fields




### -field DXGK_GLITCH_CAUSE_DRIVER_ERROR

Indicates that an internal driver error caused a glitch.  


### -field DXGK_GLITCH_CAUSE_TIMING_CHANGE

Indicates that the timing requested necessitated a glitch.  This cause should only be used if the OS requested a change which would always result in a glitch rather than something which could have been avoided under other circumstances.  

For example, this should not be used if the driver switches to a different display pipe to support an additional path, but it should be used if the OS requests a different timing to the previous one.  


### -field DXGK_GLITCH_CAUSE_PIPELINE_CHANGE

Indicates that reconfiguring the display pipeline caused a glitch.  


### -field DXGK_GLITCH_CAUSE_MEMORY_TIMING

Indicates that changing graphics memory timings caused a glitch.  


### -field DXGK_GLITCH_CAUSE_ENCODER_RECONFIG

Indicates that changing the configuration of the encoder for a target caused a glitch.  


### -field DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE

Indicates that modifying the format of pixel data in the transport stream caused a glitch.  


### -field DXGK_GLITCH_CAUSE_METADATA_CHANGE

Indicates that changing the frame metadata caused a glitch.


### -field DXGK_GLITCH_CAUSE_NONE

Indicates that there was no glitch.


### -field UINT8



