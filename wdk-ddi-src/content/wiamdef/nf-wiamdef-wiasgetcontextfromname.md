---
UID: NF:wiamdef.wiasGetContextFromName
title: wiasGetContextFromName function (wiamdef.h)
description: The wiasGetContextFromName function retrieves the item context for an item name.
old-location: image\wiasgetcontextfromname.htm
tech.root: image
ms.assetid: d15bf48e-132d-4f89-8f19-64f57deed500
ms.date: 05/03/2018
keywords: ["wiasGetContextFromName function"]
ms.keywords: image.wiasgetcontextfromname, wiamdef/wiasGetContextFromName, wiasFncs_ba1c88a2-aadc-4c2f-bb5f-88433d1e1760.xml, wiasGetContextFromName, wiasGetContextFromName function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasGetContextFromName"
 - "wiasGetContextFromName"
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
- wiasGetContextFromName
targetos: Windows
req.typenames: 
---

# wiasGetContextFromName function

## -description

The **wiasGetContextFromName** function retrieves the item context for an item name.

## -parameters

### -param pWiasContext 
[in]
Pointer to a WIA item context.

### -param lFlags

Reserved for system use and should be set to 0.

### -param bstrName 
[in]
Specifies the name of the context that is being searched for.

### -param ppWiasContext 
[out]
Pointer to a memory location that receives the address of the WIA item context.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -remarks

This function searches for item contexts whose WIA_IPA_FULL_ITEM_NAME property matches *bstrName*. Note that this property is different from WIA_IPA_ITEM_NAME, which does not contain path information.

This function should be used by minidrivers when they need to move from one application item context to another, given the item's name. The names of the application items come from their corresponding driver items, which the minidriver creates and names.

## -see-also

[wiasGetRootItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasgetrootitem)
