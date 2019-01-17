---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,BSTR)
title: CWiauPropertyList::SetCurrentValue(INT,BSTR)
description: The CWiauPropertyList::SetCurrentValue(INT,BSTR) method sets the current value of a property of type BSTR, and sets its type to VT_BSTR.
old-location: image\cwiaupropertylist_setcurrentvalue_bstr_.htm
tech.root: image
ms.assetid: 017ab648-ee62-47f5-abd3-f4eac4378b8a
ms.date: 09/07/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,BSTR), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT  ,BSTR  ), CWiauPropertyList::SetCurrentValue(INT,BSTR ), CWiauPropertyList::SetCurrentValue(INT,BSTR), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_bstr_, wiauFncs_dfd640f7-63c2-41a6-adf3-589e87aa85cc.xml, wiautil/CWiauPropertyList::SetCurrentValue
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
-	CWiauPropertyList.SetCurrentValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# CWiauPropertyList::SetCurrentValue(INT,BSTR)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,BSTR)** method sets the current value of a property of type **BSTR**, and sets its type to VT_BSTR.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
