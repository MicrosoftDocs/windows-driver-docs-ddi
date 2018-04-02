---
UID: NS:d3dkmddi._DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
title: "_DXGKCB_NOTIFY_MPO_VSYNC_FLAGS"
author: windows-driver-content
description: A structure containing the flags set by the driver to process a flip entry.
old-location: display\dxgkcb_notify_mpo_vsync_flags.htm
old-project: display
ms.assetid: 5583297C-D927-4D9A-8F77-D9871B2CA736
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure [Display Devices], _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, d3dkmddi/DXGKCB_NOTIFY_MPO_VSYNC_FLAGS, display.dxgkcb_notify_mpo_vsync_flags
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
product:
- Windows
targetos: Windows
req.typenames: DXGKCB_NOTIFY_MPO_VSYNC_FLAGS
---

# _DXGKCB_NOTIFY_MPO_VSYNC_FLAGS structure


## -description


A structure containing the flags set by the driver to process a flip entry.


## -struct-fields




### -field PostPresentNeeded

The driver sets this flag to indicate that scheduler must call DXGDDI_POSTMULTIPLANEOVERLAYPRESENT for this flip entry. 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - Value

