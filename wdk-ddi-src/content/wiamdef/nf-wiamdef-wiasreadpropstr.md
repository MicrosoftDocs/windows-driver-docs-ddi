---
UID: NF:wiamdef.wiasReadPropStr
title: wiasReadPropStr function (wiamdef.h)
description: The wiasReadPropStr function retrieves a string property value from a WIA item.
old-location: image\wiasreadpropstr.htm
tech.root: image
ms.assetid: b072b4ec-790f-454b-b94a-bfe44674f600
ms.date: 05/03/2018
keywords: ["wiasReadPropStr function"]
ms.keywords: image.wiasreadpropstr, wiamdef/wiasReadPropStr, wiasFncs_b0756dcf-44dd-4a9f-ad9a-1edff1b8e6f6.xml, wiasReadPropStr, wiasReadPropStr function [Imaging Devices]
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
 - wiasReadPropStr
 - wiamdef/wiasReadPropStr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadPropStr
---

# wiasReadPropStr function


## -description

The <b>wiasReadPropStr</b> function retrieves a string property value from a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param pbstr 

[out]
Pointer to a memory location that receives the first byte of the property's string value.

### -param pbstrOld 

[out, optional]
Pointer to a memory location that receives the first byte of the property's previous value. If this information is not needed, set this parameter to <b>NULL</b>.

### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks

When the minidriver has completed using the string it received from this function, it must deallocate the memory used for the string.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropbin">wiasReadPropBin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropfloat">wiasReadPropFloat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropguid">wiasReadPropGuid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadproplong">wiasReadPropLong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>

