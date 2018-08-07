---
UID: NF:wiautil.CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)
title: CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)
author: windows-driver-content
description: The CWiauPropertyList::SetValidValues(FLOAT, range) method sets the type, as well as default, current, and valid values for a FLOAT property associated with a range of values.
old-location: image\cwiaupropertylist_setvalidvalues_float__range_.htm
tech.root: image
ms.assetid: 4234ce4a-5b9d-47a7-b00d-e278635ee93a
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: CWiauPropertyList interface [Imaging Devices],SetValidValues method, CWiauPropertyList.SetValidValues, CWiauPropertyList.SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), CWiauPropertyList::SetValidValues, CWiauPropertyList::SetValidValues(INT  ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ,FLOAT    ), CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT), SetValidValues, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices],CWiauPropertyList interface, SetValidValues(FLOAT,(CWiauPropertyList), image.cwiaupropertylist_setvalidvalues_float__range_, wiauFncs_f8694591-e6dc-4d9a-b7dc-ab09a600c238.xml, wiautil/CWiauPropertyList::SetValidValues
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
-	CWiauPropertyList.SetValidValues
product:
-	Windows
targetos: Windows
req.typenames: 
---

# CWiauPropertyList::SetValidValues(INT,FLOAT,FLOAT,FLOAT,FLOAT,FLOAT)


## -description


The <b>CWiauPropertyList::SetValidValues(FLOAT, range)</b> method sets the type, as well as default, current, and valid values for a <b>FLOAT</b> property associated with a range of values. The method also sets the property type to VT_R4 and subtype to WIA_PROP_RANGE (defined in the Microsoft Windows SDK documentation).


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param defaultValue

Specifies the default setting of the property on the device.


### -param currentValue

Specifies the current setting of the property on the device.


### -param minValue

Specifies the minimum value in the range of values.


### -param maxValue

Specifies the maximum value in the range of values.


### -param stepValue

Specifies the increment between two successive values in the range of values.


## -returns



This method does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4f11bec0-8ff4-4fa0-824c-71ce9774d5d1">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>



<a href="https://msdn.microsoft.com/b6a554b7-9e3e-4362-9dcf-fd84d9a69150">CWiauPropertyList::SetValidValues(FLOAT, list)</a>
 

 

