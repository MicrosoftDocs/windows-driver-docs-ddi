---
UID: NF:wiautil.CWiauPropertyList.LookupPropId
title: CWiauPropertyList::LookupPropId
author: windows-driver-content
description: The CWiauPropertyList::LookupPropId method finds a property's index, given its property ID.
old-location: image\cwiaupropertylist_lookuppropid.htm
tech.root: image
ms.assetid: 454e51fc-f81a-49c8-9e07-e32819af2642
ms.date: 9/7/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],LookupPropId method, CWiauPropertyList.LookupPropId, CWiauPropertyList::LookupPropId, LookupPropId, LookupPropId method [Imaging Devices], LookupPropId method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_lookuppropid, wiauFncs_087766c2-718f-4d02-be7f-869df198c3a7.xml, wiautil/CWiauPropertyList::LookupPropId
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wiautil.h
api_name:
-	CWiauPropertyList.LookupPropId
product:
- Windows
targetos: Windows
req.typenames: 
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
