---
UID: NF:wiamdef.wiasIsPropChanged
title: wiasIsPropChanged function (wiamdef.h)
description: The wiasIsPropChanged function tests whether a specified property has been changed by an application.
old-location: image\wiasispropchanged.htm
tech.root: image
ms.assetid: 4b8f140c-ca4f-48fd-bee4-35d5a7beea52
ms.date: 05/03/2018
keywords: ["wiasIsPropChanged function"]
ms.keywords: image.wiasispropchanged, wiamdef/wiasIsPropChanged, wiasFncs_11e49124-0147-4140-ba56-879ae3fcbf46.xml, wiasIsPropChanged, wiasIsPropChanged function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasIsPropChanged"
 - "wiasIsPropChanged"
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
- wiasIsPropChanged
targetos: Windows
req.typenames: 
---

# wiasIsPropChanged function

## -description

The **wiasIsPropChanged** function tests whether a specified property has been changed by an application.

## -parameters

### -param propid

Specifies the property identifier of the property to be checked.

### -param pContext 
[in]
Pointer to a [WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context) structure that contains the current property context.

### -param pbChanged 
[out]
Pointer to a memory location that receives a BOOL value. The BOOL value is **TRUE** if the property changed, and **FALSE** if the property did not change.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

This function determines whether a property is being changed by looking at the **bChanged** member value in the property's [WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context) structure. Minidrivers typically use this function to check when an independent property has been changed so that its dependents can be updated.

## -see-also

[WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context)

[wiasGetChangedValueFloat](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluefloat)

[wiasGetChangedValueGuid](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvalueguid)

[wiasGetChangedValueLong](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluelong)

[wiasGetChangedValueStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetchangedvaluestr)
