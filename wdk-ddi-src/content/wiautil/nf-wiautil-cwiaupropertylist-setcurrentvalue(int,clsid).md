---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,CLSID)
title: CWiauPropertyList::SetCurrentValue(INT,CLSID)
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(CLSID) method sets the current value of a property of type CLSID, and sets its type to VT_CLSID.
old-location: image\cwiaupropertylist_setcurrentvalue_clsid_.htm
tech.root: image
ms.assetid: c0283b46-c1a2-469b-8167-f5dc63719c16
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,CLSID), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT ,CLSID*), CWiauPropertyList::SetCurrentValue(INT,CLSID), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_clsid_, wiauFncs_3fb0d48f-8b37-4b0a-992f-97d5f5243aaa.xml, wiautil/CWiauPropertyList::SetCurrentValue
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

# CWiauPropertyList::SetCurrentValue(INT,CLSID)


## -description


The <b>CWiauPropertyList::SetCurrentValue(CLSID)</b> method sets the current value of a property of type <b>CLSID</b>, and sets its type to VT_CLSID.


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param pValue

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a> method is called.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4f11bec0-8ff4-4fa0-824c-71ce9774d5d1">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>
 

 

