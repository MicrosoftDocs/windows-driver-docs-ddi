---
UID: NF:wiamdef.wiasFreePropContext
title: wiasFreePropContext function (wiamdef.h)
description: The wiasFreePropContext function releases the memory occupied by a WIA_PROPERTY_CONTEXT structure.
old-location: image\wiasfreepropcontext.htm
tech.root: image
ms.assetid: 14a1a5bd-acc3-4ca6-87c6-5326c0f9ca82
ms.date: 05/03/2018
keywords: ["wiasFreePropContext function"]
ms.keywords: image.wiasfreepropcontext, wiamdef/wiasFreePropContext, wiasFncs_60deac65-fa17-4f2e-abe1-fa6d424dc477.xml, wiasFreePropContext, wiasFreePropContext function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasFreePropContext"
 - "wiasFreePropContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasFreePropContext
targetos: Windows
req.typenames: 
---

# wiasFreePropContext function

## -description

The **wiasFreePropContext** function releases the memory occupied by a [WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context) structure.

## -parameters

### -param pContext [in, out]

Pointer to a [WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context) structure that contains a property context.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).

## -see-also

[WIA_PROPERTY_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wia_property_context)

[wiasCreatePropContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiascreatepropcontext)
