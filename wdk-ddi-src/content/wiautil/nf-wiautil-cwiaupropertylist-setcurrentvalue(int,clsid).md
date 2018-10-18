---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,CLSID)
title: CWiauPropertyList::SetCurrentValue(INT,CLSID)
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(INT,CLSID) method sets the current value of a property of type CLSID, and sets its type to VT_CLSID.
old-location: image\cwiaupropertylist_setcurrentvalue_clsid_.htm
tech.root: image
ms.assetid: c0283b46-c1a2-469b-8167-f5dc63719c16
ms.date: 9/7/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,CLSID), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT ,CLSID*), CWiauPropertyList::SetCurrentValue(INT,CLSID), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_clsid_, wiauFncs_3fb0d48f-8b37-4b0a-992f-97d5f5243aaa.xml, wiautil/CWiauPropertyList::SetCurrentValue
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
---

# CWiauPropertyList::SetCurrentValue(INT,CLSID)

## -description

The **CWiauPropertyList::SetCurrentValue(INT,CLSID)** method sets the current value of a property of type **CLSID**, and sets its type to VT_CLSID.

## -parameters

### -param index

Specifies the property index. Set this parameter to the value in *_pIdx_ when the [CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md) method returns.

### -param pValue

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the [CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md) method is called.

## -returns

This method does not return a value.

## -see-also

[CWiauPropertyList](nl-wiautil-cwiaupropertylist.md)

[CWiauPropertyList::DefineProperty](nf-wiautil-cwiaupropertylist-defineproperty.md)

[CWiauPropertyList::SendToWia](nf-wiautil-cwiaupropertylist-sendtowia.md)
