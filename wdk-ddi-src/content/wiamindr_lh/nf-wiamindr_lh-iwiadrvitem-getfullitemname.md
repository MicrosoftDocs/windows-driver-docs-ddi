---
UID: NF:wiamindr_lh.IWiaDrvItem.GetFullItemName
title: IWiaDrvItem::GetFullItemName (wiamindr_lh.h)
description: The IWiaDrvItem::GetFullItemName method gets the item's full name, including path information.
old-location: image\iwiadrvitem_getfullitemname.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::GetFullItemName"]
ms.keywords: DrvItem_1b166476-d17a-4953-9c73-6e3d7c9cd0f9.xml, GetFullItemName, GetFullItemName method [Imaging Devices], GetFullItemName method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetFullItemName method, IWiaDrvItem.GetFullItemName, IWiaDrvItem::GetFullItemName, image.iwiadrvitem_getfullitemname, wiamindr_lh/IWiaDrvItem::GetFullItemName
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
 - IWiaDrvItem::GetFullItemName
 - wiamindr_lh/IWiaDrvItem::GetFullItemName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaDrvItem::GetFullItemName
---

# IWiaDrvItem::GetFullItemName


## -description

The **IWiaDrvItem::GetFullItemName** method gets the item's full name, including path information.

## -parameters

### -param __MIDL__IWiaDrvItem0002

pbstrFullItemName [out, optional]

- Points to a memory location that will receive the address of a string containing the item's full name.

#### - pbstrFullItemName [out, optional]

Points to a memory location that will receive the address of a string containing the item's full name.

## -returns

If the method succeeds, it stores a pointer to the item's full name, including path information, in *pbstrFullItemName* and returns S_OK. If the method fails to allocate the string due to insufficient memory, it returns E_OUTOFMEMORY. If the parameter *pbstrFullItemName* is invalid, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## -remarks

If there is enough memory available, this method allocates a string containing the current item's full name including path information. The method returns a pointer to the string in *pbstrFullItemName*. The minidriver must deallocate the memory used by the string by calling the [SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring) function.

The name returned in *pbstrFullItemName *is the name associated with the item when the item was first created by the driver services library function [wiasCreateDrvItem](../wiamdef/nf-wiamdef-wiascreatedrvitem.md).

## -see-also

[IWiaDrvItem](./nn-wiamindr_lh-iwiadrvitem.md)

[wiasCreateDrvItem](../wiamdef/nf-wiamdef-wiascreatedrvitem.md)

