---
UID: NS:icm.DisplayStateID
title: DisplayStateID structure (icm.h)
description: The DisplayStateID structure holds the current color state IDs for a display.
ms.assetid: ed1f917e-81b8-4613-87b5-8808d28e5573
ms.date: 08/14/2020
keywords: ["DisplayStateID structure"]
ms.keywords: DisplayStateID, DisplayStateID,
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
req.typenames: DisplayStateID
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - icm.h
api_name:
 - DisplayStateID
f1_keywords:
 - DisplayStateID
 - icm/DisplayStateID
---

# DisplayStateID structure


## -description

> [!NOTE]
> This DDI construct is intended for OEM use only.

The DisplayStateID structure holds the current color state IDs for a display. These values will change as the system color state changes.

## -struct-fields

### -field profileID

Identifies the currently set color profile.

### -field transformID

Identifies the current lookup table transform.

### -field whitepointID

Identifies the current target whitepoint.

## -remarks

## -see-also

