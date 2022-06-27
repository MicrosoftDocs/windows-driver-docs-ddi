---
UID: NF:wiamdef.wiasSetValidListGuid
title: wiasSetValidListGuid function (wiamdef.h)
description: The wiasSetValidListGuid function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.
tech.root: image
ms.date: 04/19/2022
keywords: ["wiasSetValidListGuid function"]
ms.keywords: image.wiassetvalidlistguid, wiamdef/wiasSetValidListGuid, wiasFncs_eade05c7-20bd-480d-aa50-0216575ce856.xml, wiasSetValidListGuid, wiasSetValidListGuid function [Imaging Devices]
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
 - wiasSetValidListGuid
 - wiamdef/wiasSetValidListGuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetValidListGuid
---

## -description

The **wiasSetValidListGuid** function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.

## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param propid

Specifies the identifier of the property to be updated.

### -param ulCount

Specifies the number of items in the *pgValues* array.

### -param guidNom

Specifies the property's nominal value.

### -param pguidValues [in]

Pointer to the first element of an array of valid property values.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

[wiasSetValidFlag](./nf-wiamdef-wiassetvalidflag.md)

[wiasSetValidListFloat](./nf-wiamdef-wiassetvalidlistfloat.md)

[wiasSetValidListLong](./nf-wiamdef-wiassetvalidlistlong.md)

[wiasSetValidListStr](./nf-wiamdef-wiassetvalidliststr.md)

[wiasSetValidRangeFloat](./nf-wiamdef-wiassetvalidrangefloat.md)

[wiasSetValidRangeLong](./nf-wiamdef-wiassetvalidrangelong.md)