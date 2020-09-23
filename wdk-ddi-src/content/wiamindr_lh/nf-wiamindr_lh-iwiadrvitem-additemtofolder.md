---
UID: NF:wiamindr_lh.IWiaDrvItem.AddItemToFolder
title: IWiaDrvItem::AddItemToFolder (wiamindr_lh.h)
description: The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.
old-location: image\iwiadrvitem_additemtofolder.htm
tech.root: image
ms.assetid: 3f1cd0bf-13ce-49bc-a48e-dc3d89f3c7d7
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::AddItemToFolder"]
ms.keywords: AddItemToFolder, AddItemToFolder method [Imaging Devices], AddItemToFolder method [Imaging Devices],IWiaDrvItem interface, DrvItem_7979b3e5-dfd3-41bb-ae55-266cbb74866c.xml, IWiaDrvItem interface [Imaging Devices],AddItemToFolder method, IWiaDrvItem.AddItemToFolder, IWiaDrvItem::AddItemToFolder, image.iwiadrvitem_additemtofolder, wiamindr_lh/IWiaDrvItem::AddItemToFolder
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
 - IWiaDrvItem::AddItemToFolder
 - wiamindr_lh/IWiaDrvItem::AddItemToFolder
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaDrvItem.AddItemToFolder
---

# IWiaDrvItem::AddItemToFolder


## -description

The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.

## -parameters

### -param __MIDL__IWiaDrvItem0004

pIParent [in, optional]

- Points to the IWiaDrvItem parent folder item.

#### - pIParent [in, optional]

Points to the IWiaDrvItem parent folder item.

## -returns

If the method succeeds, it returns S_OK. If the method fails because an invalid *pIParent* parameter is passed, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## -remarks

Minidrivers typically use the AddItemToFolder method to add an item to a parent folder item in a driver item tree. The parent folder item is pointed to by the parameter *pIParent*. The item pointed to by *pIParent* must be a folder.

## -see-also

[IWiaDrvItem](./nn-wiamindr_lh-iwiadrvitem.md)

[RemoveItemFromFolder](./nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder.md)