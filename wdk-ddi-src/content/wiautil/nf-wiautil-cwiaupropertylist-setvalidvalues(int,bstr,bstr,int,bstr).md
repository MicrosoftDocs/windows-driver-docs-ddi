---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,BSTR,BSTR,INT,BSTR)
title: CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR) method sets the type, as well as default, current, and valid values for a BSTR property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_bstr__list_.htm
tech.root: image
ms.date: 09/21/2020
keywords: ["CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR)"]
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,BSTR,BSTR,INT,BSTR), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,BSTR  ,BSTR  ,INT,BSTR  *), CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR), CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR*), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(BSTR,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_bstr__list_, wiauFncs_7653406d-852f-452e-94c3-187be530f684.xml, wiautil/CWiauPropertyList::SetValidValues
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

# CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR) (wiautil.h)

## -description

The **CWiauPropertyList::SetValidValues(INT,BSTR,BSTR,INT,BSTR)** method sets the type, as well as default, current, and valid values for a **BSTR** property associated with a list of values. The method also sets the property type to VT_BSTR and subtype to WIA_PROP_LIST.

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

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
