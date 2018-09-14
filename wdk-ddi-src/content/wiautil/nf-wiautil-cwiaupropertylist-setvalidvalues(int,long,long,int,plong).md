---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,LONG,LONG,INT,PLONG)
title: CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG)
author: windows-driver-content
description: The CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG) method sets the type, as well as default, current, and valid values for a LONG property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_long__list_.htm
tech.root: image
ms.assetid: 1a9a04f4-1260-4773-9c94-963fc0844ccb
ms.author: windowsdriverdev
ms.date: 9/7/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,LONG,LONG,INT,PLONG), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,LONG  ,LONG  ,INT  ,PLONG  ), CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(LONG,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_long__list_, wiauFncs_6438ee42-db48-4c58-8414-5dee8fe186ef.xml, wiautil/CWiauPropertyList::SetValidValues
ms.prod: windows-hardware
ms.technology: windows-devices
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

# CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG)

## -description

The **CWiauPropertyList::SetValidValues(INT,LONG,LONG,INT,PLONG)** method sets the type, as well as default, current, and valid values for a **LONG** property associated with a list of values. The method also sets the property type to VT_I4 and subtype to WIA_PROP_LIST.

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

[CWiauPropertyList::SetValidValues(LONG, range)](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-cwiaupropertylist-setvalidvalues%28int_long_long_long_long_long%29)
