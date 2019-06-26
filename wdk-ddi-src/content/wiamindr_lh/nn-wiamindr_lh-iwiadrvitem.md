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


The <b>IWiaDrvItem</b> interface provides methods that a WIA minidriver can use to manage a tree of <b>IWiaDrvItem</b> items.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaDrvItem</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaDrvItem</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaDrvItem</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-additemtofolder">AddItemToFolder</a>
</td>
<td align="left" width="63%">
The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-dumpitemdata">DumpItemData</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::DumpItemData</b> method dumps private data associated with an <b>IWiaDrvItem</b> item into an allocated private buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-findchilditembyname">FindChildItemByName</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::FindChildItemByName</b> method searches the driver item tree for a specific child item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-finditembyname">FindItemByName</a>
</td>
<td align="left" width="63%">
The<b> IWiaDrvItem::FindItemByName</b> method locates an item in a driver item tree by the item's full name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getdevicespeccontext">GetDeviceSpecContext</a>
</td>
<td align="left" width="63%">
The<b> IWiaDrvItem::GetDeviceSpecContext</b> method gets a device-specific context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfirstchilditem">GetFirstChildItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetFirstChildItem</b> method gets the first child item in an <b>IWiaDrvItem</b> folder item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname">GetFullItemName</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetFullItemName</b> method gets the item's full name, including path information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getitemflags">GetItemFlags</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetItemFlags</b> method gets the item flags of the current <b>IWiaDrvItem</b> item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getitemname">GetItemName</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetItemName</b> method gets the current <b>IWiaDrvItem</b> item name, not including path information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem">GetNextSiblingItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetNextSiblingItem</b> method gets the next sibling of the current item in an <b>IWiaDrvItem</b> folder.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getparentitem">GetParentItem</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::GetParentItem</b> gets the parent item of the current item.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder">RemoveItemFromFolder</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::RemoveItemFromFolder</b> method removes an item from a parent folder.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-unlinkitemtree">UnlinkItemTree</a>
</td>
<td align="left" width="63%">
The <b>IWiaDrvItem::UnlinkItemTree</b> method unlinks the driver item tree and releases all items in the tree.

</td>
</tr>
</table> 

