---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,CLSID,CLSID,INT,CLSID)
title: CWiauPropertyList::SetValidValues(INT,CLSID,CLSID,INT,CLSID) (wiautil.h)
description: The CWiauPropertyList::SetValidValues(INT,CLSID,CLSID,INT,CLSID) method sets the type, as well as default, current, and valid values for a CLSID property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_clsid__list_.htm
tech.root: image
ms.assetid: d401ed85-de6b-4758-b7c4-d6fcd59c157e
ms.date: 09/07/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,CLSID,CLSID,INT,CLSID), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT,CLSID*,CLSID*,INT,CLSID**), CWiauPropertyList::SetValidValues(INT,CLSID,CLSID,INT,CLSID), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(CLSID,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_clsid__list_, wiauFncs_fb681759-0ab5-47ba-8e35-4a0a8d28e52f.xml, wiautil/CWiauPropertyList::SetValidValues
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

# CWiauPropertyList::SetValidValues(INT,CLSID,CLSID,INT,CLSID)

## -description

The **CWiauPropertyList::SetValidValues(INT,CLSID,CLSID,INT,CLSID)** method sets the type, as well as default, current, and valid values for a **CLSID** property associated with a list of values. The method also sets the property type to VT_CLSID and subtype to WIA_PROP_LIST.

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

Pointer to a memory location that contains the address of the first property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
