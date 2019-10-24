---
UID: NN:wiamindr_lh.IWiaDrvItem
title: IWiaDrvItem (wiamindr_lh.h)
description: The IWiaDrvItem interface provides methods that a WIA minidriver can use to manage a tree of IWiaDrvItem items.
old-location: image\iwiadrvitem_interface.htm
tech.root: image
ms.assetid: 0609e1b2-48df-413c-90bd-d7ddea26510a
ms.date: 05/03/2018
ms.keywords: DrvItem_9dbe78e4-0823-4edc-b86e-75e25d4de981.xml, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], IWiaDrvItem interface [Imaging Devices],described, image.iwiadrvitem_interface, wiamindr_lh/IWiaDrvItem
ms.topic: interface
f1_keywords:
 - "wiamindr_lh/IWiaDrvItem"
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
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
- IWiaDrvItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem interface

## -description

The **IWiaDrvItem** interface provides methods that a WIA minidriver can use to manage a tree of **IWiaDrvItem** items.

## -inheritance

## -members

The **IWiaDrvItem** interface has these methods.

| Method | Description |
| --- | --- |
| [AddItemToFolder](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-additemtofolder) | The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree. |
| [DumpItemData](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-dumpitemdata) | The **IWiaDrvItem::DumpItemData** method dumps private data associated with an **IWiaDrvItem** item into an allocated private buffer. |
| [FindChildItemByName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-findchilditembyname) | The **IWiaDrvItem::FindChildItemByName** method searches the driver item tree for a specific child item. |
| [FindItemByName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-finditembyname) | The **IWiaDrvItem::FindItemByName** method locates an item in a driver item tree by the item's full name. |
| [GetDeviceSpecContext](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getdevicespeccontext) | The **IWiaDrvItem::GetDeviceSpecContext** method gets a device-specific context. |
| [GetFirstChildItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfirstchilditem) | The **IWiaDrvItem::GetFirstChildItem** method gets the first child item in an **IWiaDrvItem** folder item. |
| [GetFullItemName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname) | The **IWiaDrvItem::GetFullItemName** method gets the item's full name, including path information. |
| [GetItemFlags](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getitemflags) | The **IWiaDrvItem::GetItemFlags** method gets the item flags of the current **IWiaDrvItem** item. |
| [GetItemName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getitemname) | The **IWiaDrvItem::GetItemName** method gets the current **IWiaDrvItem** item name, not including path information. |
| [GetNextSiblingItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem) | The **IWiaDrvItem::GetNextSiblingItem** method gets the next sibling of the current item in an **IWiaDrvItem** folder. |
| [GetParentItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getparentitem) | The **IWiaDrvItem::GetParentItem** gets the parent item of the current item. |
| [RemoveItemFromFolder](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder) | The **IWiaDrvItem::RemoveItemFromFolder** method removes an item from a parent folder. |
| [UnlinkItemTree](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-unlinkitemtree) | The **IWiaDrvItem::UnlinkItemTree** method unlinks the driver item tree and releases all items in the tree. |
