---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,BYTE,INT)
title: CWiauPropertyList::SetCurrentValue(INT,BYTE,INT)
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(BYTE*) method sets the current value of a property consisting of an array of bytes, and sets its type to VT_UI1 | VT_VECTOR.
old-location: image\cwiaupropertylist_setcurrentvalue_byte__.htm
tech.root: image
ms.assetid: 85e4c30e-61c2-4e9e-b272-7ad77883ccd8
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,BYTE,INT), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT  ,BYTE  *,INT  ), CWiauPropertyList::SetCurrentValue(INT,BYTE,INT), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_byte__, wiauFncs_b79d2982-a76b-4675-a342-32a2751bac26.xml, wiautil/CWiauPropertyList::SetCurrentValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
product: Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList::SetCurrentValue(INT,BYTE,INT)


## -description


The <b>CWiauPropertyList::SetCurrentValue(BYTE*)</b> method sets the current value of a property consisting of an array of bytes, and sets its type to VT_UI1 | VT_VECTOR.


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a> method is called.


### -param size

Specifies the number of elements in the array of bytes.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4f11bec0-8ff4-4fa0-824c-71ce9774d5d1">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>
 

 

