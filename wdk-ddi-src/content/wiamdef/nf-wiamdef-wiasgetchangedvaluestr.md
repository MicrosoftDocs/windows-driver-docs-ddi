---
UID: NF:wiamdef.wiasGetChangedValueStr
title: wiasGetChangedValueStr function (wiamdef.h)
description: The wiasGetChangedValueStr function determines whether a property with a string value has been changed by an application.
old-location: image\wiasgetchangedvaluestr.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasGetChangedValueStr function"]
ms.keywords: image.wiasgetchangedvaluestr, wiamdef/wiasGetChangedValueStr, wiasFncs_24524e94-fa0a-4d40-b742-6fad76707014.xml, wiasGetChangedValueStr, wiasGetChangedValueStr function [Imaging Devices]
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasGetChangedValueStr
 - wiamdef/wiasGetChangedValueStr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasGetChangedValueStr
---

# wiasGetChangedValueStr function


## -description

The **wiasGetChangedValueStr** function determines whether a property with a string value has been changed by an application.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param pContext 

[in]
Pointer to a [WIA_PROPERTY_CONTEXT](../wiamindr_lh/ns-wiamindr_lh-_wia_property_context.md) structure that contains the current property context.

### -param bNoValidation

Indicates whether the property's current value should be validated against its set of valid values. If this parameter is set to **TRUE**, the function does not perform validation on the property. If it is **FALSE**, the function performs data validation.

### -param propID

Specifies the property identifier of the property being tested.

### -param pInfo

Pointer to a [WIAS_CHANGED_VALUE_INFO](../wiamindr_lh/ns-wiamindr_lh-_wias_changed_value_info.md) structure that contains the current and previous values of the property.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -remarks

The driver should validate the property only after the driver has updated the values of the property. The driver updates the values as a result of property changes requested by the application.

## -see-also

[WIAS_CHANGED_VALUE_INFO](../wiamindr_lh/ns-wiamindr_lh-_wias_changed_value_info.md)

[WIA_PROPERTY_CONTEXT](../wiamindr_lh/ns-wiamindr_lh-_wia_property_context.md)

[wiasGetChangedValueFloat](./nf-wiamdef-wiasgetchangedvaluefloat.md)

[wiasGetChangedValueGuid](./nf-wiamdef-wiasgetchangedvalueguid.md)

[wiasGetChangedValueLong](./nf-wiamdef-wiasgetchangedvaluelong.md)
