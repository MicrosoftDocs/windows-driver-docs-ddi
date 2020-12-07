---
UID: NF:wiamindr_lh.IWiaDrvItem.UnlinkItemTree
title: IWiaDrvItem::UnlinkItemTree (wiamindr_lh.h)
description: The IWiaDrvItem::UnlinkItemTree method unlinks the driver item tree and releases all items in the tree.
old-location: image\iwiadrvitem_unlinkitemtree.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::UnlinkItemTree"]
ms.keywords: DrvItem_70e5eaf0-4115-4207-9ea2-53ca8c210795.xml, IWiaDrvItem interface [Imaging Devices],UnlinkItemTree method, IWiaDrvItem.UnlinkItemTree, IWiaDrvItem::UnlinkItemTree, UnlinkItemTree, UnlinkItemTree method [Imaging Devices], UnlinkItemTree method [Imaging Devices],IWiaDrvItem interface, image.iwiadrvitem_unlinkitemtree, wiamindr_lh/IWiaDrvItem::UnlinkItemTree
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
 - IWiaDrvItem::UnlinkItemTree
 - wiamindr_lh/IWiaDrvItem::UnlinkItemTree
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaDrvItem.UnlinkItemTree
---

# IWiaDrvItem::UnlinkItemTree


## -description

The **IWiaDrvItem::UnlinkItemTree** method unlinks the driver item tree and releases all items in the tree.

## -parameters

### -param __MIDL__IWiaDrvItem0005

lFlags [in]

- Indicates how the driver item tree should be unlinked. This parameter must be set to one of the following values. For more information, see [WIA Item Type Flags](/windows/win32/wia/-wia-wia-item-type-flags).

  | Value | Meaning |
  | --- | --- |
  | WiaItemTypeDeleted | The item is marked as deleted from the tree. |
  | WiaItemTypeDisconnected | The item represents a disconnected device. |

#### - lFlags [in]

Indicates how the driver item tree should be unlinked. This parameter must be set to one of the following values. For more information, see [WIA Item Type Flags](/windows/win32/wia/-wia-wia-item-type-flags).

| Value | Meaning |
| --- | --- |
| WiaItemTypeDeleted | The item is marked as deleted from the tree. |
| WiaItemTypeDisconnected | The item represents a disconnected device. |

## -returns

If the method succeeds, it returns S_OK. If the method is called on a nonroot item, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## -remarks

Minidrivers must call this method on the root item in the driver item tree when they want to invalidate the tree. This is typically done when the driver is being unloaded or when the minidriver needs to rebuild the driver item tree.
