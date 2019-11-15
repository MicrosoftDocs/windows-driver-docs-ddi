---
UID: NF:wiautil.CWiauPropertyList.CWiauPropertyList
title: CWiauPropertyList::CWiauPropertyList (wiautil.h)
description: The CWiauPropertyList::CWiauPropertyList method is the constructor for the CWiauPropertyList class.
old-location: image\cwiaupropertylist_cwiaupropertylist.htm
tech.root: image
ms.assetid: 5e493d3c-81b6-4db5-a550-c86eadf5a723
ms.date: 09/07/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList interface [Imaging Devices],CWiauPropertyList method, CWiauPropertyList method [Imaging Devices], CWiauPropertyList method [Imaging Devices],CWiauPropertyList interface, CWiauPropertyList.CWiauPropertyList, CWiauPropertyList::CWiauPropertyList, image.cwiaupropertylist_cwiaupropertylist, wiauFncs_834023ef-b425-4469-a5e7-c127fd5acf2a.xml, wiautil/CWiauPropertyList::CWiauPropertyList
ms.topic: method
f1_keywords:
 - "wiautil/CWiauPropertyList.CWiauPropertyList"
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
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
- Wiautil.h
api_name:
- CWiauPropertyList.CWiauPropertyList
product:
- Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList::CWiauPropertyList


## -description

The **CWiauPropertyList::CWiauPropertyList** method is the constructor for the **CWiauPropertyList** class.

## -parameters


## -remarks

The **CWiauPropertyList** constructor initializes all data members of a property list object to either **NULL** or zero. Use the [CWiauPropertyList::Init]() method to reserve memory for properties. Use the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method once per property to add it to the property list object.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::Init](nf-wiautil-cwiaupropertylist-init.md)

[CWiauPropertyList::~CWiauPropertyList](nf-wiautil-cwiaupropertylist-~cwiaupropertylist.md)
