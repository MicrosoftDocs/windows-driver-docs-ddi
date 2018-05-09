---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue(INT,LONG)
title: CWiauPropertyList::SetCurrentValue(INT,LONG)
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(LONG) method sets the current value of a property of type LONG, and sets its type to VT_I4.
old-location: image\cwiaupropertylist_setcurrentvalue_long_.htm
old-project: image
ms.assetid: 583c8ec9-7a57-4da3-beaf-9f9db943a652
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetCurrentValue method, CWiauPropertyList.SetCurrentValue, CWiauPropertyList.SetCurrentValue(INT,LONG), CWiauPropertyList::SetCurrentValue, CWiauPropertyList::SetCurrentValue(INT,LONG), SetCurrentValue, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices],CWiauPropertyList interface, SetCurrentValue(LONG)(CWiauPropertyList), image.cwiaupropertylist_setcurrentvalue_long_, wiauFncs_e59bb543-0827-4c93-955c-6a2bef4b67b7.xml, wiautil/CWiauPropertyList::SetCurrentValue
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

# CWiauPropertyList::SetCurrentValue(INT,LONG)


## -description


The <b>CWiauPropertyList::SetCurrentValue(LONG)</b> method sets the current value of a property of type <b>LONG</b>, and sets its type to VT_I4.


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param value

Specifies the value that is written to the device property in the property list.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4f11bec0-8ff4-4fa0-824c-71ce9774d5d1">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>
 

 

