---
UID: NF:wiamdef.wiasSetValidListStr
title: wiasSetValidListStr function (wiamdef.h)
description: The wiasSetValidListStr function sets the valid values for a WIA_PROP_LIST property of type VT_BSTR.
tech.root: image
ms.date: 04/19/2022
keywords: ["wiasSetValidListStr function"]
ms.keywords: image.wiassetvalidliststr, wiamdef/wiasSetValidListStr, wiasFncs_c18aeb74-5c44-43ea-be9e-5132f45a5f77.xml, wiasSetValidListStr, wiasSetValidListStr function [Imaging Devices]
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
 - wiasSetValidListStr
 - wiamdef/wiasSetValidListStr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetValidListStr
---

## -description

The **wiasSetValidListStr** function sets the valid values for a WIA_PROP_LIST property of type VT_BSTR.

## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param propid

Specifies the identifier of the property to be updated.

### -param ulCount

Specifies the number of items in the *pbstrValues* array.

### -param bstrNom

Specifies the nominal value of the property.

### -param bstrValues [in]

Pointer to the first element of an array of valid property values.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors.

## -see-also

[wiasSetValidFlag](./nf-wiamdef-wiassetvalidflag.md)

[wiasSetValidListFloat](./nf-wiamdef-wiassetvalidlistfloat.md)

[wiasSetValidListGuid](./nf-wiamdef-wiassetvalidlistguid.md)

[wiasSetValidListLong](./nf-wiamdef-wiassetvalidlistlong.md)

[wiasSetValidRangeFloat](./nf-wiamdef-wiassetvalidrangefloat.md)

[wiasSetValidRangeLong](./nf-wiamdef-wiassetvalidrangelong.md)