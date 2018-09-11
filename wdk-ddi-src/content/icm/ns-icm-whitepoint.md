---
UID: NS:icm.WhitePoint
title: WhitePoint structure
author: windows-driver-content
description: The Whitepoint structure encapsulates a display whitepoint.
ms.assetid: 15925576-f238-430f-885b-879de5716710
ms.author: windowsdriverdev
ms.date: 9/10/2018
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: WhitePoint, WhitePoint, 
req.header: icm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WhitePoint
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	icm.h
api_name: 
-	WhitePoint
product:
-	Windows
targetos: Windows
---

# WhitePoint structure

## -description

> [!NOTE]
> This DDI construct is intended for OEM use only.

The Whitepoint structure encapsulates a display whitepoint in various ways:

    - **CHROMATICITY**: An xyY point, populate xyY member

    - **TEMPERATURE**: A CCT point, populate CCT member

    - **D65**: The standard D65 s[c]RGB whitepoint.

## -struct-fields


## -remarks

Set the type enum to the preferred expression type and populate the corresponding data entry in the union. 

## -see-also