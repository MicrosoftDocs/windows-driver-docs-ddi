---
UID: NF:wiamdef.wiasSetValidListLong
title: wiasSetValidListLong function (wiamdef.h)
description: The wiasSetValidListLong function sets the valid values for a WIA_PROP_LIST property of type VT_I4.
old-location: image\wiassetvalidlistlong.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasSetValidListLong function"]
ms.keywords: image.wiassetvalidlistlong, wiamdef/wiasSetValidListLong, wiasFncs_0ccc4e24-3b86-426e-94c6-7c8bb19811f8.xml, wiasSetValidListLong, wiasSetValidListLong function [Imaging Devices]
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
 - wiasSetValidListLong
 - wiamdef/wiasSetValidListLong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetValidListLong
---

# wiasSetValidListLong function


## -description

The <b>wiasSetValidListLong </b>function sets the valid values for a WIA_PROP_LIST property of type VT_I4.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the identifier of the property to be updated.

### -param ulCount

Specifies the number of items in the <i>plValues</i> array.

### -param lNom

Specifies the property's nominal value.

### -param plValues

Pointer to the first element of an array of valid property values.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidflag">wiasSetValidFlag</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistfloat">wiasSetValidListFloat</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistguid">wiasSetValidListGuid</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangefloat">wiasSetValidRangeFloat</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangelong">wiasSetValidRangeLong</a>
