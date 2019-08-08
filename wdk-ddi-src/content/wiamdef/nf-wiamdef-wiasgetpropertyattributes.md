---
UID: NF:wiamdef.wiasGetPropertyAttributes
title: wiasGetPropertyAttributes function (wiamdef.h)
description: The wiasGetPropertyAttributes function retrieves the access flags and valid values for a set of properties.
old-location: image\wiasgetpropertyattributes.htm
tech.root: image
ms.assetid: b12ff158-73e7-4fdf-b7b1-2969d161ed93
ms.date: 05/03/2018
ms.keywords: image.wiasgetpropertyattributes, wiamdef/wiasGetPropertyAttributes, wiasFncs_d1a6ee77-54bc-400f-a670-e39889c71835.xml, wiasGetPropertyAttributes, wiasGetPropertyAttributes function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasGetPropertyAttributes"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasGetPropertyAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasGetPropertyAttributes function

## -description

The **wiasGetPropertyAttributes** function retrieves the access flags and valid values for a set of properties.

## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param cPropSpec

Specifies the number of properties.

### -param pPropSpec [in]

Pointer to a [PROPSPEC](https://docs.microsoft.com/windows/win32/api/propidlbase/ns-propidlbase-propspec) structure indicating the properties for which to get valid values and access flags.

### -param pulAccessFlags

Pointer to an array that contains the access flags for the properties.

### -param pPropVar [out]

Pointer to an array of [PROPVARIANT](https://docs.microsoft.com/windows/win32/api/propidlbase/ns-propidlbase-propvariant) structures that contains the valid values for the properties.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

This function fills each element of the *pPropVar* array with a PROPVARIANT structure that specifies the valid values for the corresponding property. Properties with the access rights flag WIA_PROP_NONE have no valid values for that property. The data type for the valid values of these properties is VT_EMPTY.

One or more of the [WIA_PROP_Xxx property attributes](https://docs.microsoft.com/windows/win32/wia/-wia-property-attributes) and access flags can be returned in each element of the *pulAccessFlags* array.

If the property has a range of valid values, the values can be determined through the *pPropVar* parameter upon completion of this function. The *pPropVar* parameter specifies an array of PROPVARIANT structures.

Valid integer and floating-point values in a range are accessed using the following index constants.

| Valid value index | Description |
| --- | --- |
| WIA_RANGE_MIN | Minimum value |
| WIA_RANGE_NOM | Nominal value |
| WIA_RANGE_MAX | Maximum value |
| WIA_RANGE_STEP | Increment value |

Valid list values are accessed using the following index constants.

| Valid value index | Description |
| --- | --- |
| WIA_LIST_COUNT | Count of valid list values, not counting the nominal value |
| WIA_LIST_NOM | Nominal value |
| WIA_LIST_VALUES | Index to first valid value |

Valid bitwise flag values are accessed using the following index constants.

| Valid value index | Description |
| --- | --- |
| WIA_FLAG_NOM | Nominal value |
| WIA_FLAG_VALUES | All valid flags are joined together by an OR operator |
