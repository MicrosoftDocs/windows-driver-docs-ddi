---
UID: NF:wiamindr_lh.IWiaDrvItem.FindChildItemByName
title: IWiaDrvItem::FindChildItemByName (wiamindr_lh.h)
description: The IWiaDrvItem::FindChildItemByName method searches the driver item tree for a specific child item.
old-location: image\iwiadrvitem_findchilditembyname.htm
tech.root: image
ms.assetid: 04f446f2-cd59-4191-be0c-60140ecee3b2
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::FindChildItemByName"]
ms.keywords: DrvItem_afe8c47f-ebf9-484e-94bf-fdcd4713ea2a.xml, FindChildItemByName, FindChildItemByName method [Imaging Devices], FindChildItemByName method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],FindChildItemByName method, IWiaDrvItem.FindChildItemByName, IWiaDrvItem::FindChildItemByName, image.iwiadrvitem_findchilditembyname, wiamindr_lh/IWiaDrvItem::FindChildItemByName
f1_keywords:
 - "wiamindr_lh/IWiaDrvItem.FindChildItemByName"
 - "IWiaDrvItem.FindChildItemByName"
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
- IWiaDrvItem.FindChildItemByName
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::FindChildItemByName

## -description

The **IWiaDrvItem::FindChildItemByName** method searches the driver item tree for a specific child item.

## -parameters

### -param __MIDL__IWiaDrvItem0010

bstrChildItemName [in]

- Specifies a string containing the name with path information of the child item to find.

### -param __MIDL__IWiaDrvItem0011

ppIChildItem [out, optional]

- Points to a memory location that will receive the address of the found **IWiaDrvItem** child item.

#### - bstrChildItemName [in]

Specifies a string containing the name with path information of the child item to find.

#### - ppIChildItem [out, optional]

Points to a memory location that will receive the address of the found **IWiaDrvItem** child item.

## -returns

If the method succeeds, it stores a pointer to the found child item in *ppIChildItem* and returns S_OK. If the method fails to find the child item, it returns S_FALSE. If the method fails for another reason, it returns a standard COM error code.

## -remarks

Minidrivers typically use this method to search a driver item tree for a specific child item when the child item's name is known. The child item's full name is obtained in the  method [IWiaDrvItem::GetFullItemName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname).

## -see-also

[IWiaDrvItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem)

[IWiaDrvItem::FindItemByName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-finditembyname)

[IWiaDrvItem::GetFullItemName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname)
