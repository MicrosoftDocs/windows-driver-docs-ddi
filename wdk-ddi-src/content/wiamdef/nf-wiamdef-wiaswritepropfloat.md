---
UID: NF:wiamdef.wiasWritePropFloat
title: wiasWritePropFloat function (wiamdef.h)
description: The wiasWritePropFloat function writes a single floating-point property value to a WIA item.
old-location: image\wiaswritepropfloat.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasWritePropFloat function"]
ms.keywords: image.wiaswritepropfloat, wiamdef/wiasWritePropFloat, wiasFncs_49539474-675e-420d-b7a4-67f147017975.xml, wiasWritePropFloat, wiasWritePropFloat function [Imaging Devices]
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
 - wiasWritePropFloat
 - wiamdef/wiasWritePropFloat
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasWritePropFloat
---

# wiasWritePropFloat function


## -description

The <b>wiasWritePropFloat </b>function writes a single floating-point property value to a WIA item.

## -parameters

### -param pWiasContext [in]


A Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param fVal

Specifies the floating-point property value to write to the item.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropfloat">wiasReadPropFloat</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropbin">wiasWritePropBin</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswriteproplong">wiasWritePropLong</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropstr">wiasWritePropStr</a>
