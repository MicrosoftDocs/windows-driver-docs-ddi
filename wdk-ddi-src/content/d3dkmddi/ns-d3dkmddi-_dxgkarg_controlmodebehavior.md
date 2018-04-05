---
UID: NS:d3dkmddi._DXGKARG_CONTROLMODEBEHAVIOR
title: _DXGKARG_CONTROLMODEBEHAVIOR
author: windows-driver-content
description:
ms.assetid: 708d7d44-6261-438f-93e7-f12e338e870e
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_CONTROLMODEBEHAVIOR, DXGKARG_CONTROLMODEBEHAVIOR, *INOUT_PDXGKARG_CONTROLMODEBEHAVIOR
req.header: d3dkmddi.h
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
req.typenames: DXGKARG_CONTROLMODEBEHAVIOR
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	_DXGKARG_CONTROLMODEBEHAVIOR
product: Windows
targetos: Windows
---

# _DXGKARG_CONTROLMODEBEHAVIOR structure

## -description

Arguments used to control the color enhancements.

## -struct-fields

### -field Request

The known color enhancements that affect the color accuracy of the display that the OS is not aware of.

### -field Satisfied

Driver supports controlling the color enhancements and successfully changed the state requested.

### -field NotSatisfied

Driver supports controlling the color enhancements but was unsuccessful in changing the state requested.

