---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)
title: CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)
author: windows-driver-content
description: The CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT) method sets the type, as well as default, current, and valid values for a FLOAT property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_float__list_.htm
tech.root: image
ms.assetid: b6a554b7-9e3e-4362-9dcf-fd84d9a69150
ms.date: 09/07/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,FLOAT    ,FLOAT  ,INT  ,PFLOAT  ), CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(FLOAT,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_float__list_, wiauFncs_18bd612f-ceb6-44ab-9242-1ef033f1bce8.xml, wiautil/CWiauPropertyList::SetValidValues
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
---

# CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)

## -description

The **CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,INT,PFLOAT)** method sets the type, as well as default, current, and valid values for a **FLOAT** property associated with a list of values. The method also sets the property type to VT_R4 and subtype to WIA_PROP_LIST.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param defaultValue

Specifies the default setting of the property on the device.

### -param currentValue

Specifies the current setting of the property on the device.

### -param numValues

Specifies the number of values in the property list.

### -param pValues

Points to the first property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)

[CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT) method](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues%28int_float_float_float_float_float%29)
