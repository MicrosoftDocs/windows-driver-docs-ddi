---
UID: NF:wiamdef.wiasCreateDrvItem
title: wiasCreateDrvItem function (wiamdef.h)
description: The wiasCreateDrvItem function creates an IWiaDrvItem Interface object.
old-location: image\wiascreatedrvitem.htm
tech.root: image
ms.assetid: bc91133a-ae6a-447a-8519-65fbe2929521
ms.date: 05/03/2018
keywords: ["wiasCreateDrvItem function"]
ms.keywords: image.wiascreatedrvitem, wiamdef/wiasCreateDrvItem, wiasCreateDrvItem, wiasCreateDrvItem function [Imaging Devices], wiasFncs_9bede31d-0ac0-4cc7-bdd5-7734e5f82dfc.xml
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
 - wiasCreateDrvItem
 - wiamdef/wiasCreateDrvItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasCreateDrvItem
---

# wiasCreateDrvItem function


## -description

The **wiasCreateDrvItem** function creates an [IWiaDrvItem Interface](../wiamindr_lh/nn-wiamindr_lh-iwiadrvitem.md) object.

## -parameters

### -param lObjectFlags

Specifies the object item type, which must be **WiaItemTypeFolder** or **WiaItemTypeFile** (possibly the bitwise OR of these). These flags are described in [WIA Item Type Flags](/windows/win32/wia/-wia-wia-item-type-flags).

### -param bstrItemName

Specifies a string that contains the item name without path information.

### -param bstrFullItemName

Specifies a string that contains the item name with path information.

### -param pIMiniDrv 

[in, out]
Pointer to the [IWiaMiniDrv Interface](../wiamindr_lh/nn-wiamindr_lh-iwiaminidrv.md) of the current minidriver.

### -param cbDevSpecContext

Specifies the size in bytes of the device specific context.

### -param ppDevSpecContext 

[out]
Pointer to a memory location that receives the address of the device specific context. Set this to **NULL** if the information is not needed.

### -param ppIWiaDrvItem 

[out]
Pointer to a memory location that receives the address of an [IWiaDrvItem Interface](../wiamindr_lh/nn-wiamindr_lh-iwiadrvitem.md) for the newly created **IWiaDrvItem** object.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -remarks

This function creates and initializes an [IWiaDrvItem COM Interface](/windows-hardware/drivers/image/iwiadrvitem-com-interface) object with the specified name and attributes. It also creates a context for the **IWiaDrvItem** object. Minidrivers typically use this function to build a tree of device items.

## -see-also

[wiasCreateChildAppItem](./nf-wiamdef-wiascreatechildappitem.md)