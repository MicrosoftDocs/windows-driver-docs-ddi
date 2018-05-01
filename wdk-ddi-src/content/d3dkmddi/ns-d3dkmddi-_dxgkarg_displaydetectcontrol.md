---
UID: NS:d3dkmddi._DXGKARG_DISPLAYDETECTCONTROL
title: "_DXGKARG_DISPLAYDETECTCONTROL"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_DISPLAYDETECTCONTROL.
old-location: display\dxgkarg_displaydetectcontrol.htm
old-project: display
ms.assetid: A0B5798E-FF4D-4133-BFA9-39B37CC387F6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_DISPLAYDETECTCONTROL, DXGKARG_DISPLAYDETECTCONTROL structure [Display Devices], PDXGKARG_DISPLAYDETECTCONTROL, PDXGKARG_DISPLAYDETECTCONTROL structure pointer [Display Devices], _DXGKARG_DISPLAYDETECTCONTROL, d3dkmddi/DXGKARG_DISPLAYDETECTCONTROL, d3dkmddi/PDXGKARG_DISPLAYDETECTCONTROL, display.dxgkarg_displaydetectcontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_DISPLAYDETECTCONTROL
product: Windows
targetos: Windows
req.typenames: DXGKARG_DISPLAYDETECTCONTROL
---

# _DXGKARG_DISPLAYDETECTCONTROL structure


## -description


Used to hold the arguments for <a href="https://msdn.microsoft.com/6F10EA4D-BCDE-475E-9937-414CB83F6F2F">DXGKDDI_DISPLAYDETECTCONTROL</a>.


## -struct-fields




### -field TargetId

 


### -field Type

Detection action type requested.


### -field NonDestructiveOnly

Only used for polling the types of requests.
If TRUE, the driver should attempt to poll the specified target(s) without causing any visual artifacts. 
If FALSE, the driver should perform any action necessary to detect the status of the specified target(s) even if it would cause visual artifacts on the target(s) in question or other targets.



### -field Reserved

This value is reserved for system use.


#### - TargetID

The identifier of a display adapter's video present target.  Ignored if the type is not DXGK_DDCT_POLLONE.

