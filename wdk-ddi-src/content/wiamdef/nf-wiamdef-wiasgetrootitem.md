---
UID: NF:wiamdef.wiasGetRootItem
title: wiasGetRootItem function (wiamdef.h)
description: The wiasGetRootItem function retrieves the root item context of a specified WIA item.
old-location: image\wiasgetrootitem.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasGetRootItem function"]
ms.keywords: image.wiasgetrootitem, wiamdef/wiasGetRootItem, wiasFncs_4e991723-5462-456e-b56f-82a38e5cf556.xml, wiasGetRootItem, wiasGetRootItem function [Imaging Devices]
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
 - wiasGetRootItem
 - wiamdef/wiasGetRootItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasGetRootItem
---

# wiasGetRootItem function


## -description

The **wiasGetRootItem** function retrieves the root item context of a specified WIA item.

## -parameters

### -param pWiasContext [in]


Pointer to a WIA item context.

### -param ppWiasContext [out]


Pointer to a memory location that receives the address of the WIA item's root item context.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -see-also

[wiasGetDrvItem](./nf-wiamdef-wiasgetdrvitem.md)
