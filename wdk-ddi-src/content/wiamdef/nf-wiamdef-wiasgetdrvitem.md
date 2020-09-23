---
UID: NF:wiamdef.wiasGetDrvItem
title: wiasGetDrvItem function (wiamdef.h)
description: The wiasGetDrvItem function retrieves a driver item.
old-location: image\wiasgetdrvitem.htm
tech.root: image
ms.assetid: c09924ef-cd2c-419c-81d5-bbd40b886767
ms.date: 05/03/2018
keywords: ["wiasGetDrvItem function"]
ms.keywords: image.wiasgetdrvitem, wiamdef/wiasGetDrvItem, wiasFncs_47e70917-9675-4291-a76a-46aa734efef3.xml, wiasGetDrvItem, wiasGetDrvItem function [Imaging Devices]
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
 - wiasGetDrvItem
 - wiamdef/wiasGetDrvItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasGetDrvItem
---

# wiasGetDrvItem function


## -description

The **wiasGetDrvItem** function retrieves a driver item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param ppIWiaDrvItem

Pointer to a memory location that receives the address of an [IWiaDrvItem Interface](../wiamindr_lh/nn-wiamindr_lh-iwiadrvitem.md).

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -see-also

[wiasCreateDrvItem](./nf-wiamdef-wiascreatedrvitem.md)

[wiasGetRootItem](./nf-wiamdef-wiasgetrootitem.md)