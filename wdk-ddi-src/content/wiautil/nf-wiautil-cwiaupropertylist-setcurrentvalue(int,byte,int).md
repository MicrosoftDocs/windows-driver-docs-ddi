---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,BYTE,INT)
title: CWiauPropertyList::SetCurrentValue(INT,BYTE,INT) (wiautil.h)
description: The CWiauPropertyList::SetCurrentValue(INT,BYTE,INT) method sets the current value of a property consisting of an array of bytes, and sets its type to VT_UI1 | VT_VECTOR.
old-location: image\cwiaupropertylist_setcurrentvalue_byte__.htm
tech.root: image
ms.assetid: 85e4c30e-61c2-4e9e-b272-7ad77883ccd8
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SetCurrentValue(INT,BYTE,INT)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,BYTE,INT), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT  ,BYTE  *,INT  ), CWiauPropertyList::SetCurrentValue(INT,BYTE,INT), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_byte__, wiauFncs_b79d2982-a76b-4675-a342-32a2751bac26.xml, wiautil/CWiauPropertyList::SetCurrentValue
f1_keywords:
 - "wiautil/CWiauPropertyList.SetCurrentValue"
 - "CWiauPropertyList.SetCurrentValue"
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
- CWiauPropertyList.SetCurrentValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# CWiauPropertyList::SetCurrentValue(INT,BYTE,INT)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,BYTE,INT)** method sets the current value of a property consisting of an array of bytes, and sets its type to VT_UI1 | VT_VECTOR.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

### -param size

Specifies the number of elements in the array of bytes.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
