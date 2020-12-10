---
UID: NF:wiamindr_lh.IWiaDrvItem.DumpItemData
title: IWiaDrvItem::DumpItemData (wiamindr_lh.h)
description: The IWiaDrvItem::DumpItemData method dumps private data associated with an IWiaDrvItem item into an allocated private buffer.
old-location: image\iwiadrvitem_dumpitemdata.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["IWiaDrvItem::DumpItemData"]
ms.keywords: DrvItem_fae1b45f-719d-4bce-92fd-d43844178800.xml, DumpItemData, DumpItemData method [Imaging Devices], DumpItemData method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],DumpItemData method, IWiaDrvItem.DumpItemData, IWiaDrvItem::DumpItemData, image.iwiadrvitem_dumpitemdata, wiamindr_lh/IWiaDrvItem::DumpItemData
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
 - IWiaDrvItem::DumpItemData
 - wiamindr_lh/IWiaDrvItem::DumpItemData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wiamindr_lh.h
api_name:
 - IWiaDrvItem.DumpItemData
---

# IWiaDrvItem::DumpItemData


## -description

The **IWiaDrvItem::DumpItemData** method dumps private data associated with an **IWiaDrvItem** item into an allocated private buffer.

## -parameters

### -param __MIDL__IWiaDrvItem0015

bstrDrvItemData [out, optional]

- Points to an allocated buffer that will receive the **IWiaDrvItem** data.

#### - bstrDrvItemData [out, optional]

Points to an allocated buffer that will receive the **IWiaDrvItem** data.

## -returns

If the method succeeds, it returns S_OK. If the method fails the buffer allocation, it returns E_OUTOFMEMORY. If the method fails for another reason, it returns a standard COM error code.

## -remarks

This method is provided for Microsoft internal debugging only. It will return E_NOTIMPL on the release operating system.

