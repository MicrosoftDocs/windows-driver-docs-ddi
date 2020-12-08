---
UID: NF:wiamdef.wiasReadPropGuid
title: wiasReadPropGuid function (wiamdef.h)
description: The wiasReadPropGuid function retrieves a GUID property value from a WIA item.
old-location: image\wiasreadpropguid.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasReadPropGuid function"]
ms.keywords: image.wiasreadpropguid, wiamdef/wiasReadPropGuid, wiasFncs_80e78a38-5f47-4bd3-b071-62eebc65fd6f.xml, wiasReadPropGuid, wiasReadPropGuid function [Imaging Devices]
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
 - wiasReadPropGuid
 - wiamdef/wiasReadPropGuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadPropGuid
---

# wiasReadPropGuid function


## -description

The <b>wiasReadPropGuid </b>function retrieves a GUID property value from a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param pguidVal

### -param pguidValOld

### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.


#### - pgVal [out]

Pointer to a memory location that receives the GUID property value.


#### - pgValOld [out, optional]

Pointer to a memory location that receives the previous value of the GUID property data. If this information is not needed, this parameter can be set to <b>NULL</b>.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropbin">wiasReadPropBin</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropfloat">wiasReadPropFloat</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadproplong">wiasReadPropLong</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasreadpropstr">wiasReadPropStr</a>



<a href="/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiaswritepropguid">wiasWritePropGuid</a>
