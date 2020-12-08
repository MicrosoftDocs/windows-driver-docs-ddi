---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)
title: CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) method sets the type, as well as default, current, and valid values for a FLOAT property associated with a range of values.
old-location: image\cwiaupropertylist_setvalidvalues_float__range_.htm
tech.root: image
ms.date: 09/21/2020
keywords: ["CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ), CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(FLOAT,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_float__range_, wiauFncs_f8694591-e6dc-4d9a-b7dc-ab09a600c238.xml, wiautil/CWiauPropertyList::SetValidValues
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
 - CWiauPropertyList::SetValidValues
 - wiautil/CWiauPropertyList::SetValidValues
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wiautil.h
api_name:
 - CWiauPropertyList.SetValidValues
---

# CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) (wiautil.h)

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

[CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)](nf-wiautil-cwiaupropertylist-setvalidvalues(int_float_float_int_pfloat).md)
