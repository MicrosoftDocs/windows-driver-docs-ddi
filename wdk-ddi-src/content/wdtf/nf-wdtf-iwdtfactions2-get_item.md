---
UID: NF:wdtf.IWDTFActions2.get_Item
title: IWDTFActions2::get_Item (wdtf.h)
description: Gets an individual action in the collection.
old-location: dtf\iwdtfactions2_item.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFActions2::get_Item"]
ms.keywords: IWDTFActions2 interface [Windows Device Testing Framework],Item method, IWDTFActions2.get_Item, IWDTFActions2::Item, IWDTFActions2::get_Item, Item method [Windows Device Testing Framework], Item method [Windows Device Testing Framework],IWDTFActions2 interface, dtf.iwdtfactions2_item, get_Item, wdtf/IWDTFActions2::Item
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Wdtf.idl
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
 - IWDTFActions2::get_Item
 - wdtf/IWDTFActions2::get_Item
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtf.h
api_name:
 - IWDTFDeviceDepot2.Item
 - IWDTFDeviceDepot2.get_Item
---

# IWDTFActions2::get_Item


## -description

Gets an individual action in the collection.

## -parameters

### -param Index 

[in]
The 0-based index value.

### -param ppAction 

[out]
The indexed action.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">IWDTFActions2</a>
