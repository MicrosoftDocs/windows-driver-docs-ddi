---
UID: NF:wiamdef.wiasSetValidRangeLong
title: wiasSetValidRangeLong function (wiamdef.h)
description: The wiasSetValidRangeLong function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_I4.
old-location: image\wiassetvalidrangelong.htm
tech.root: image
ms.assetid: ff4badb5-ab27-4deb-864a-51165290bca4
ms.date: 05/03/2018
ms.keywords: image.wiassetvalidrangelong, wiamdef/wiasSetValidRangeLong, wiasFncs_3ee53b59-4ef4-4c35-8544-1ac7a8729212.xml, wiasSetValidRangeLong, wiasSetValidRangeLong function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasSetValidRangeLong"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasSetValidRangeLong
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasSetValidRangeLong function


## -description


The <b>wiasSetValidRangeLong </b>function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_I4.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param lMin

Specifies the minimum value of the valid range.


### -param lNom

Specifies the property's nominal value.


### -param lMax

Specifies the maximum value of the valid range.


### -param lStep

Specifies the increment between each valid value in the range.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidflag">wiasSetValidFlag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistfloat">wiasSetValidListFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistguid">wiasSetValidListGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidlistlong">wiasSetValidListLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidliststr">wiasSetValidListStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiassetvalidrangefloat">wiasSetValidRangeFloat</a>
 

 

