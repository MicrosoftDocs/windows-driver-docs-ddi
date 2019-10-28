---
UID: NF:wiamindr_lh.IWiaDrvItem.GetItemName
title: IWiaDrvItem::GetItemName (wiamindr_lh.h)
description: The IWiaDrvItem::GetItemName method gets the current IWiaDrvItem item name, not including path information.
old-location: image\iwiadrvitem_getitemname.htm
tech.root: image
ms.assetid: 1e731975-13f8-4b5d-93de-714f62e9591f
ms.date: 05/03/2018
ms.keywords: DrvItem_18b6c67e-9d95-45d4-844f-90fcb5c277bd.xml, GetItemName, GetItemName method [Imaging Devices], GetItemName method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetItemName method, IWiaDrvItem.GetItemName, IWiaDrvItem::GetItemName, image.iwiadrvitem_getitemname, wiamindr_lh/IWiaDrvItem::GetItemName
ms.topic: method
f1_keywords:
 - "wiamindr_lh/IWiaDrvItem.GetItemName"
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
- IWiaDrvItem.GetItemName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::GetItemName

## -description

The **IWiaDrvItem::GetItemName** method gets the current **IWiaDrvItem** item name, not including path information.

## -parameters

### -param __MIDL__IWiaDrvItem0003

pbstrItemName [out, optional]

- Points to a memory location that will receive the address of the string containing the item name.

#### - pbstrItemName [out, optional]

Points to a memory location that will receive the address of the string containing the item name. 

## -returns

If the method succeeds, it stores a pointer to the item's name (path information is not included) in *pbstrItemName* and returns S_OK. If the method fails to allocate the string due to insufficient memory, it returns E_OUTOFMEMORY. If the parameter *pbstrItemName* is invalid, the method returns E_INVALIDARG.If the method fails for another reason, it returns a standard COM error code.

## -remarks

If there is enough memory available, the method allocates a string containing the current item's name, excluding path information. The method returns a pointer to the string in *pbstrItemName*. The minidriver must deallocate the memory used by the string by calling the [**SysFreeString**](https://docs.microsoft.com/windows/win32/api/oleauto/nf-oleauto-sysfreestring) function.

## -see-also

[IWiaDrvItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem)

[IWiaDrvItem::GetFullItemName](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname)
