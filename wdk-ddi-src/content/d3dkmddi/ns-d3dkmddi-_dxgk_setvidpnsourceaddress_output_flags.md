---
UID: NS:d3dkmddi._DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
title: "_DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS" (d3dkmddi.h)
description: A structure containing the flags used to set the VidPN source address.
old-location: display\dxgk_setvidpnsourceaddress_output_flags.htm
ms.assetid: CFEEB41D-050F-4372-AB54-39ABC696C89D
ms.date: 05/10/2018
ms.keywords: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure [Display Devices], _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, d3dkmddi/DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS, display.dxgk_setvidpnsourceaddress_output_flags
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
-	DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS
---

# _DXGK_SETVIDPNSOURCEADDRESS_OUTPUT_FLAGS structure


## -description


A structure containing the flags used to set the VidPN source address.


## -struct-fields




### -field PrePresentNeeded

Indicates that the driver must be called again at the PASSIVE_LEVEL to perform the requested operation.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

