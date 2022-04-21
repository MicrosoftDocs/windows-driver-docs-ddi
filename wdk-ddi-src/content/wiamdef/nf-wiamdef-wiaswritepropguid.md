---
UID: NF:wiamdef.wiasWritePropGuid
title: wiasWritePropGuid function (wiamdef.h)
description: The wiasWritePropGuid function writes a single GUID property value to a WIA item.
tech.root: image
ms.date: 04/19/2022
keywords: ["wiasWritePropGuid function"]
ms.keywords: image.wiaswritepropguid, wiamdef/wiasWritePropGuid, wiasFncs_2d4110e9-d2e5-47a2-8213-d221e77c527d.xml, wiasWritePropGuid, wiasWritePropGuid function [Imaging Devices]
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
 - wiasWritePropGuid
 - wiamdef/wiasWritePropGuid
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasWritePropGuid
---

## -description

The **wiasWritePropGuid** function writes a single GUID property value to a WIA item.

## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param guidVal

Specifies a GUID property value to write to the item.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -see-also

[wiasReadPropGuid](./nf-wiamdef-wiasreadpropguid.md)

[wiasWritePropBin](./nf-wiamdef-wiaswritepropbin.md)

[wiasWritePropFloat](./nf-wiamdef-wiaswritepropfloat.md)

[wiasWritePropLong](./nf-wiamdef-wiaswriteproplong.md)

[wiasWritePropStr](./nf-wiamdef-wiaswritepropstr.md)