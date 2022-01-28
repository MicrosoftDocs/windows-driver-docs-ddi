---
UID: NF:acxmisc.DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME
tech.root: audio
title: DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME
ms.date: 01/28/2022
targetos: Windows
description: The DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME function declares a constant that can be used to work with a AcxObjectBag. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmisc.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmisc.h
api_name:
 - DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME
f1_keywords:
 - DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME
 - acxmisc/DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME
dev_langs:
 - c++
---

## -description

The DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME function declares a constant that can be used to work with a AcxObjectBag. 

## -parameters

### -param name

The name of the declared constant.

## -remarks

### Example

This example shows the definition of DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME.

```cpp
#define DECLARE_CONST_ACXOBJECTBAG_USB_PROPERTY_NAME(name) \
    DECLARE_CONST_UNICODE_STRING(name, L"usb_" #name)
```

## -see-also

[acxmisc.h header](index.md)

