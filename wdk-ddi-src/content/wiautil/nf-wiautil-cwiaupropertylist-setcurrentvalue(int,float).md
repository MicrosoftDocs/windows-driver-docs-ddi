---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,FLOAT)
title: CWiauPropertyList::SetCurrentValue(INT,FLOAT) (wiautil.h)
description: The CWiauPropertyList::SetCurrentValue(INT,FLOAT) method sets the current value of a property of type FLOAT, and sets its type to VT_R4.
old-location: image\cwiaupropertylist_setcurrentvalue_float_.htm
tech.root: image
ms.assetid: dfcbe65b-7da1-4427-a58f-cbec4ce355bf
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SetCurrentValue(INT,FLOAT)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,FLOAT), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT,FLOAT), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_float_, wiauFncs_871f53bf-7ad7-459e-9760-04c67a55f800.xml, wiautil/CWiauPropertyList::SetCurrentValue
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

# CWiauPropertyList::SetCurrentValue(INT,FLOAT)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,FLOAT)** method sets the current value of a property of type **FLOAT**, and sets its type to VT_R4.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param value

Specifies the value that is written to the device property in the property list.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)
