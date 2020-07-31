---
UID: NF:wiamdef.wiasWritePropStr
title: wiasWritePropStr function (wiamdef.h)
description: The wiasWritePropStr function writes a single string property value to a WIA item.
old-location: image\wiaswritepropstr.htm
tech.root: image
ms.assetid: 542e4196-164b-4ae1-87ad-2d6adb9c8904
ms.date: 05/03/2018
keywords: ["wiasWritePropStr function"]
ms.keywords: image.wiaswritepropstr, wiamdef/wiasWritePropStr, wiasFncs_f1b2ee2f-f9a1-4d10-9ffa-47a6c10c4a92.xml, wiasWritePropStr, wiasWritePropStr function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasWritePropStr"
 - "wiasWritePropStr"
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
- wiasWritePropStr
targetos: Windows
req.typenames: 
---

# wiasWritePropStr function


## -description


The <b>wiasWritePropStr</b> function writes a single string property value to a WIA item.


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param bstr [in, optional]

Specifies the string property value to write to the item.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropstr">wiasReadPropStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropbin">wiasWritePropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropfloat">wiasWritePropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>
 

 

