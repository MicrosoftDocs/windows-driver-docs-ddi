---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)
title: CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) method sets the type, as well as default, current, and valid values for a FLOAT property associated with a range of values.
old-location: image\cwiaupropertylist_setvalidvalues_float__range_.htm
tech.root: image
ms.assetid: 4234ce4a-5b9d-47a7-b00d-e278635ee93a
ms.date: 09/07/2018
keywords: ["CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ), CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(FLOAT,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_float__range_, wiauFncs_f8694591-e6dc-4d9a-b7dc-ab09a600c238.xml, wiautil/CWiauPropertyList::SetValidValues
f1_keywords:
 - "wiautil/CWiauPropertyList.SetValidValues"
 - "CWiauPropertyList.SetValidValues"
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
- CWiauPropertyList.SetValidValues
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)

## -description

The **CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)** method sets the type, as well as default, current, and valid values for a **FLOAT** property associated with a range of values. The method also sets the property type to VT_R4 and subtype to WIA_PROP_RANGE.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param defaultValue

Specifies the default setting of the property on the device.

### -param currentValue

Specifies the current setting of the property on the device.

### -param minValue

Specifies the minimum value in the range of values.

### -param maxValue

Specifies the maximum value in the range of values.

### -param stepValue

Specifies the increment between two successive values in the range of values.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)

[CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues(int_float_float_int_pfloat))
