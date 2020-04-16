---
UID: NF:wiamdef.wiasGetChildrenContexts
title: wiasGetChildrenContexts function (wiamdef.h)
description: The wiasGetChildrenContexts function retrieves an array of item contexts belonging to the current item's children.
old-location: image\wiasgetchildrencontexts.htm
tech.root: image
ms.assetid: a69216f4-1272-488f-8d06-8dc3b6a88452
ms.date: 05/03/2018
keywords: ["wiasGetChildrenContexts function"]
ms.keywords: image.wiasgetchildrencontexts, wiamdef/wiasGetChildrenContexts, wiasFncs_fff487b8-2797-4df4-ae22-f25c08f21dfc.xml, wiasGetChildrenContexts, wiasGetChildrenContexts function [Imaging Devices]
f1_keywords:
 - "wiamdef/wiasGetChildrenContexts"
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
- wiasGetChildrenContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasGetChildrenContexts function

## -description

The **wiasGetChildrenContexts** function retrieves an array of item contexts belonging to the current item's children.

## -parameters

### -param pParentContext [in]

Pointer to the parent item.

### -param pulNumChildren [out]

Pointer to a memory location that receives the number of children contexts.

### -param pppChildren [out]

Pointer to a memory location that points to an array whose elements are addresses of [IWiaItem](https://docs.microsoft.com/windows/win32/api/wia_xp/nn-wia_xp-iwiaitem) objects. Each **IWiaItem** object represents one child context.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).
