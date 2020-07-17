---
UID: NF:wiamindr_lh.IWiaDrvItem.GetFirstChildItem
title: IWiaDrvItem::GetFirstChildItem (wiamindr_lh.h)
description: The IWiaDrvItem::GetFirstChildItem method gets the first child item in an IWiaDrvItem folder item.
old-location: image\iwiadrvitem_getfirstchilditem.htm
tech.root: image
ms.assetid: 2e580a57-03cb-4ff4-b3c6-0b5ef17b4ccb
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::GetFirstChildItem"]
ms.keywords: DrvItem_0ee76640-f07a-4b25-9955-230122a2a662.xml, GetFirstChildItem, GetFirstChildItem method [Imaging Devices], GetFirstChildItem method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetFirstChildItem method, IWiaDrvItem.GetFirstChildItem, IWiaDrvItem::GetFirstChildItem, image.iwiadrvitem_getfirstchilditem, wiamindr_lh/IWiaDrvItem::GetFirstChildItem
f1_keywords:
 - "wiamindr_lh/IWiaDrvItem.GetFirstChildItem"
 - "IWiaDrvItem.GetFirstChildItem"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaDrvItem.GetFirstChildItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::GetFirstChildItem

## -description

The **IWiaDrvItem::GetFirstChildItem** method gets the first child item in an **IWiaDrvItem** folder item.

## -parameters

### -param __MIDL__IWiaDrvItem0013

ppIChildItem [out, optional]

- Points to a memory location that will receive the address of an **IWiaDrvItem** child item.

#### - ppIChildItem [out, optional]

Points to a memory location that will receive the address of an **IWiaDrvItem** child item.

## -returns

If the method succeeds, it stores a pointer to the first child item in *ppIChildItem* and returns S_OK. If a child item cannot be found, the method returns S_FALSE. If the item being searched is not a folder, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## -remarks

Minidrivers typically use this method to retrieve the first child item in a driver item folder. The item being searched must be a folder item.

## -see-also

[IWiaDrvItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem)

[IWiaDrvItem::GetNextSiblingItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem)

[IWiaDrvItem::GetParentItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getparentitem)
