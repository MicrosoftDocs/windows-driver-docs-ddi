---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,LONG,LONG,LONG,LONG,LONG)
title: CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG,LONG,LONG) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG,LONG,LONG) method sets the type, as well as default, current, and valid values for a LONG property associated with a range of values.
old-location: image\cwiaupropertylist_setvalidvalues_long__range_.htm
tech.root: image
ms.assetid: da84a381-b564-4356-bd08-dd145b3dcc0b
ms.date: 09/07/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,LONG,LONG,LONG,LONG,LONG), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,LONG  ,LONG  ,LONG  ,LONG  ,LONG  ), CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG,LONG,LONG), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(LONG,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_long__range_, wiauFncs_49a3f9ad-d74b-436c-ba14-8047889431ea.xml, wiautil/CWiauPropertyList::SetValidValues
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
-	CWiauPropertyList.SetValidValues
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG,LONG,LONG)

## -description

The **CWiauPropertyList::SetValidValues(INT,LONG,LONG,LONG,LONG,LONG)** method sets the type, as well as default, current, and valid values for a **LONG** property associated with a range of values. The method also sets the property type to VT_I4 and subtype to WIA_PROP_RANGE.

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

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)

[CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG)](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues%28int_long_long_int_plong%29)
