---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,PSYSTEMTIME)
title: CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME)
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(SYSTEMTIME) method sets the current value of a property of type SYSTEMTIME, and sets its type to VT_UI2 | VT_VECTOR.
old-location: image\cwiaupropertylist_setcurrentvalue_systemtime_.htm
tech.root: image
ms.assetid: 1823dec6-aec8-47eb-9543-9acfd32c4b0d
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,PSYSTEMTIME), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME  ), CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, image.cwiaupropertylist_setcurrentvalue_systemtime_, wiauFncs_dafa3146-7ba7-4782-9e6f-95a80d97452e.xml, wiautil/CWiauPropertyList::SetCurrentValue
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
product:
-	Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList::SetCurrentValue(INT,PSYSTEMTIME)


## -description


The <b>CWiauPropertyList::SetCurrentValue(SYSTEMTIME)</b> method sets the current value of a property of type <b>SYSTEMTIME</b>, and sets its type to VT_UI2 | VT_VECTOR.


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a> method is called.


## -returns



This method does not return a value.




## -remarks



The <b>SYSTEMTIME</b> structure is described in the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/4f11bec0-8ff4-4fa0-824c-71ce9774d5d1">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>
 

 

