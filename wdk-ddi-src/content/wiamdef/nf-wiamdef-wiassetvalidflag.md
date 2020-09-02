---
UID: NF:wiamdef.wiasSetValidFlag
title: wiasSetValidFlag function (wiamdef.h)
description: The wiasSetValidFlag function sets the valid values for a WIA_PROP_FLAG property.
old-location: image\wiassetvalidflag.htm
tech.root: image
ms.assetid: 86690e6f-4b30-4de9-b380-8939ed983027
ms.date: 05/03/2018
keywords: ["wiasSetValidFlag function"]
ms.keywords: image.wiassetvalidflag, wiamdef/wiasSetValidFlag, wiasFncs_4c84b6c9-20fe-4894-b3fc-f7d84742827a.xml, wiasSetValidFlag, wiasSetValidFlag function [Imaging Devices]
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
 - wiasSetValidFlag
 - wiamdef/wiasSetValidFlag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasSetValidFlag
---

# wiasSetValidFlag function


## -description

The <b>wiasSetValidFlag </b>function sets the valid values for a WIA_PROP_FLAG property.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the identifier of the property to be updated.

### -param ulNom

Specifies the property's nominal value.

### -param ulValidBits

Specifies the valid bits that can be used for the WIA_PROP_FLAG property.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistfloat">wiasSetValidListFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistguid">wiasSetValidListGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistlong">wiasSetValidListLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangefloat">wiasSetValidRangeFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangelong">wiasSetValidRangeLong</a>

