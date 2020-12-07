---
UID: NF:wiautil.CWiauPropertyList.Init
title: CWiauPropertyList::Init (wiautil.h)
description: The CWiauPropertyList::Init method initializes a property list object.
old-location: image\cwiaupropertylist_init.htm
tech.root: image
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::Init"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],Init method, CWiauPropertyList.Init, CWiauPropertyList::Init, Init, Init method [Imaging Devices], Init method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_init, wiauFncs_4bc30663-6fd6-45b7-a18f-1adc766489be.xml, wiautil/CWiauPropertyList::Init
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
targetos: Windows
req.typenames: 
f1_keywords:
 - CWiauPropertyList::Init
 - wiautil/CWiauPropertyList::Init
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.Init
---

# CWiauPropertyList::Init


## -description

The **CWiauPropertyList::Init** method initializes a property list object.

## -parameters

### -param NumProps

Specifies the number of properties within the property list for which to reserve space. This number can be larger than the actual number of properties in the property list, but it cannot be smaller.

## -returns

On success, the **CWiauPropertyList::Init** method returns S_OK. If the method has already been called on a given property list, the method returns E_FAIL.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::CWiauPropertyList](nf-wiautil-cwiaupropertylist-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

