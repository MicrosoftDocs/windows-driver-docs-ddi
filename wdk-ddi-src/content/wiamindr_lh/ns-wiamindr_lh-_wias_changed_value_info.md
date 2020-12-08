---
UID: NS:wiamindr_lh._WIAS_CHANGED_VALUE_INFO
title: _WIAS_CHANGED_VALUE_INFO (wiamindr_lh.h)
description: The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.
old-location: image\wias_changed_value_info.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["WIAS_CHANGED_VALUE_INFO structure"]
ms.keywords: "*PWIAS_CHANGED_VALUE_INFO, PWIAS_CHANGED_VALUE_INFO, PWIAS_CHANGED_VALUE_INFO structure pointer [Imaging Devices], WIAS_CHANGED_VALUE_INFO, WIAS_CHANGED_VALUE_INFO structure [Imaging Devices], _WIAS_CHANGED_VALUE_INFO, image.wias_changed_value_info, wiamindr_lh/PWIAS_CHANGED_VALUE_INFO, wiamindr_lh/WIAS_CHANGED_VALUE_INFO, wiastrct_0c1c5e66-1f26-471f-9916-117460b6a373.xml"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
targetos: Windows
req.typenames: WIAS_CHANGED_VALUE_INFO, *PWIAS_CHANGED_VALUE_INFO
f1_keywords:
 - _WIAS_CHANGED_VALUE_INFO
 - wiamindr_lh/_WIAS_CHANGED_VALUE_INFO
 - PWIAS_CHANGED_VALUE_INFO
 - wiamindr_lh/PWIAS_CHANGED_VALUE_INFO
 - WIAS_CHANGED_VALUE_INFO
 - wiamindr_lh/WIAS_CHANGED_VALUE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamindr_lh.h
api_name:
 - WIAS_CHANGED_VALUE_INFO
---

# _WIAS_CHANGED_VALUE_INFO structure


## -description

The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.

## -struct-fields

### -field bChanged

Is a Boolean that indicates whether a property has changed. That is, if the property's current value is different from its value before [IWiaMiniDrv::drvValidateItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties.md) was called. Upon return from one of the **wiasGetChangedValue**_Xxx_ functions, this member is **TRUE** if the property changed, and **FALSE** if the property did not change.

### -field vt

Specifies the variant data type for the property. This member can be one of the following:

VT_UI1

VT_UI2

VT_UI4

VT_I2

VT_I4

VT_R4

VT_R8

VT_CLSID

VT_BSTR

See the [PROPVARIANT](/windows/win32/api/propidl/ns-propidl-propvariant) structure for more information.

### -field Old

### -field Old.lVal

### -field Old.fltVal

### -field Old.bstrVal

### -field Old.guidVal

### -field Current

### -field Current.lVal

### -field Current.fltVal

### -field Current.bstrVal

### -field Current.guidVal

## -remarks

The **wiasGetChangedValue**_Xxx_ functions, use this structure to determine whether a property of a certain type has been changed by an application. These functions are used when the minidriver performs property validation, which occurs within the body of [IWiaMiniDrv::drvValidateItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties.md).

## -see-also

[IWiaMiniDrv::drvValidateItemProperties](./nf-wiamindr_lh-iwiaminidrv-drvvalidateitemproperties.md)

[wiasGetChangedValueFloat](../wiamdef/nf-wiamdef-wiasgetchangedvaluefloat.md)

[wiasGetChangedValueGuid](../wiamdef/nf-wiamdef-wiasgetchangedvalueguid.md)

[wiasGetChangedValueLong](../wiamdef/nf-wiamdef-wiasgetchangedvaluelong.md)

[wiasGetChangedValueStr](../wiamdef/nf-wiamdef-wiasgetchangedvaluestr.md)
