---
UID: NS:hidpi._HIDP_BUTTON_ARRAY_DATA
tech.root: hid
title: HIDP_BUTTON_ARRAY_DATA
ms.date: 11/11/2021
targetos: Windows
description: The HIDP_BUTTON_ARRAY_DATA structure is used to get or set data for single button in a button array.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: hidpi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: HIDP_BUTTON_ARRAY_DATA, *PHIDP_BUTTON_ARRAY_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - _HIDP_BUTTON_ARRAY_DATA
 - PHIDP_BUTTON_ARRAY_DATA
 - HIDP_BUTTON_ARRAY_DATA
f1_keywords:
 - _HIDP_BUTTON_ARRAY_DATA
 - hidpi/_HIDP_BUTTON_ARRAY_DATA
 - PHIDP_BUTTON_ARRAY_DATA
 - hidpi/PHIDP_BUTTON_ARRAY_DATA
 - HIDP_BUTTON_ARRAY_DATA
 - hidpi/HIDP_BUTTON_ARRAY_DATA
dev_langs:
 - c++
---

## -description

The **HIDP_BUTTON_ARRAY_DATA** structure is used to get or set data for single button in a button array.

## -struct-fields

### -field ArrayIndex

The position of the button within the button array. The value will always be less than [HIDP_BUTTON_CAPS.ReportCount](ns-hidpi-_hidp_button_caps.md). This is not an index of a button array within the parsed data.

### -field On

**TRUE** when the button at the *ArrayIndex* within the button array is on. **FALSE** when the button is off.

## -remarks

## -see-also

- [HIDP_BUTTON_CAPS](ns-hidpi-_hidp_button_caps.md)
