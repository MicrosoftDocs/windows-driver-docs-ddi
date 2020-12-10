---
UID: NF:wiamindr_lh.IWiaDrvItem.GetParentItem
title: IWiaDrvItem::GetParentItem (wiamindr_lh.h)
description: The IWiaDrvItem::GetParentItem gets the parent item of the current item.
old-location: image\iwiadrvitem_getparentitem.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::GetParentItem"]
ms.keywords: DrvItem_47782466-b345-43e7-9fd1-8c4b355c6d46.xml, GetParentItem, GetParentItem method [Imaging Devices], GetParentItem method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetParentItem method, IWiaDrvItem.GetParentItem, IWiaDrvItem::GetParentItem, image.iwiadrvitem_getparentitem, wiamindr_lh/IWiaDrvItem::GetParentItem
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaDrvItem::GetParentItem
 - wiamindr_lh/IWiaDrvItem::GetParentItem
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaDrvItem.GetParentItem
---

# IWiaDrvItem::GetParentItem


## -description

The **IWiaDrvItem::GetParentItem** gets the parent item of the current item.

## -parameters

### -param __MIDL__IWiaDrvItem0012

ppIParentItem [out, optional]

- Returns a pointer to the parent item of the current item.

#### - ppIParentItem [out, optional]

Returns a pointer to the parent item of the current item.

## -returns

If the method succeeds, it stores a pointer to the parent item in *pplParentItem* and returns S_OK. If the parent item is the root item, the method returns S_FALSE. If the method fails, it returns a standard COM error code.

## -remarks

Minidrivers typically use this method to obtain a pointer to the nonroot parent item of the current item.

## -see-also

[IWiaDrvItem](./nn-wiamindr_lh-iwiadrvitem.md)

[IWiaDrvItem::GetFirstChildItem](./nf-wiamindr_lh-iwiadrvitem-getfirstchilditem.md)

[IWiaDrvItem::GetNextSiblingItem](./nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem.md)
