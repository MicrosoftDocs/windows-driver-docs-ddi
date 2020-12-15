---
UID: NF:wiautil.CWiauPropertyList.LookupPropId
title: CWiauPropertyList::LookupPropId (wiautil.h)
description: The CWiauPropertyList::LookupPropId method finds a property's index, given its property ID.
old-location: image\cwiaupropertylist_lookuppropid.htm
tech.root: image
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::LookupPropId"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],LookupPropId method, CWiauPropertyList.LookupPropId, CWiauPropertyList::LookupPropId, LookupPropId, LookupPropId method [Imaging Devices], LookupPropId method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_lookuppropid, wiauFncs_087766c2-718f-4d02-be7f-869df198c3a7.xml, wiautil/CWiauPropertyList::LookupPropId
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
 - CWiauPropertyList::LookupPropId
 - wiautil/CWiauPropertyList::LookupPropId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.LookupPropId
---

# CWiauPropertyList::LookupPropId


## -description

The **CWiauPropertyList::LookupPropId** method finds a property's index, given its property ID.

## -parameters

### -param PropId

Specifies the property ID for the property.

## -returns

On success, the method returns the index of the property within the property list. If it is unable to find the property, the method returns -1.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::GetPropId](nf-wiautil-cwiaupropertylist-getpropid.md)

