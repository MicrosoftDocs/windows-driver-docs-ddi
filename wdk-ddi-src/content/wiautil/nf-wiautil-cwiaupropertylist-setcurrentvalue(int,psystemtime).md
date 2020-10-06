---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,PSYSTEMTIME)
title: CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME) (wiautil.h)
description: The CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME) method sets the current value of a property of type SYSTEMTIME, and sets its type to VT_UI2 | VT_VECTOR.
old-location: image\cwiaupropertylist_setcurrentvalue_systemtime_.htm
tech.root: image
ms.assetid: 1823dec6-aec8-47eb-9543-9acfd32c4b0d
ms.date: 09/21/2020
keywords: ["CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,PSYSTEMTIME), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME  ), CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_systemtime_, wiauFncs_dafa3146-7ba7-4782-9e6f-95a80d97452e.xml, wiautil/CWiauPropertyList::SetCurrentValue
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
ms.custom: RS5
f1_keywords:
 - CWiauPropertyList::SetCurrentValue
 - wiautil/CWiauPropertyList::SetCurrentValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.SetCurrentValue
---

# CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME) (wiautil.h)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME)** method sets the current value of a property of type **SYSTEMTIME**, and sets its type to VT_UI2 | VT_VECTOR.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in **pIdx* when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

## -remarks

The **SYSTEMTIME** structure is described in the Microsoft Windows SDK documentation.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
