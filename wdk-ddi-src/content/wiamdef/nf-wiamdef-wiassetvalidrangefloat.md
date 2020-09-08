---
UID: NF:wiamdef.wiasSetValidRangeFloat
title: wiasSetValidRangeFloat function (wiamdef.h)
description: The wiasSetValidRangeFloat function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_R4.
old-location: image\wiassetvalidrangefloat.htm
tech.root: image
ms.assetid: 66bc5e03-4cc2-4de3-b707-18ff7e0deb4b
ms.date: 05/03/2018
keywords: ["wiasSetValidRangeFloat function"]
ms.keywords: image.wiassetvalidrangefloat, wiamdef/wiasSetValidRangeFloat, wiasFncs_d8eb35e4-e295-43cf-a457-5e6fac3f537d.xml, wiasSetValidRangeFloat, wiasSetValidRangeFloat function [Imaging Devices]
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
 - wiasSetValidRangeFloat
 - wiamdef/wiasSetValidRangeFloat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetValidRangeFloat
---

# wiasSetValidRangeFloat function


## -description

The <b>wiasSetValidRangeFloat </b>function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_R4.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the identifier of the property to be updated.

### -param fMin

Specifies the minimum value of the valid range.

### -param fNom

Specifies the property's nominal value.

### -param fMax

Specifies the maximum value of the valid range.

### -param fStep

Specifies the increment between each valid value in the range.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidflag">wiasSetValidFlag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistfloat">wiasSetValidListFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistguid">wiasSetValidListGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistlong">wiasSetValidListLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangelong">wiasSetValidRangeLong</a>

