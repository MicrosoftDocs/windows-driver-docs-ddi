---
UID: NF:wiautil.CWiauPropertyList.SetValidValues
title: CWiauPropertyList::SetValidValues method
author: windows-driver-content
description: The CWiauPropertyList::SetValidValues(BSTR, list) method sets the type, as well as default, current, and valid values for a BSTR property associated with a list of values.
old-location: image\cwiaupropertylist_setvalidvalues_bstr__list_.htm
old-project: image
ms.assetid: b806e310-4e6d-4258-8dd5-0c9aa35a35f4
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], SetValidValues method, CWiauPropertyList::SetValidValues, L, P, S, SetValidValues method [Imaging Devices], SetValidValues method [Imaging Devices], CWiauPropertyList interface, SetValidValues,CWiauPropertyList.SetValidValues, V, W, a, d, e, i, image.cwiaupropertylist_setvalidvalues_bstr__list_, l, o, p, r, s, t, u, wiauFncs_7653406d-852f-452e-94c3-187be530f684.xml, wiautil/CWiauPropertyList::SetValidValues, y"
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
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wiautil.h
apiname:
-	CWiauPropertyList.SetValidValues
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::SetValidValues method


## -description


The <b>CWiauPropertyList::SetValidValues(BSTR, list)</b> method sets the type, as well as default, current, and valid values for a <b>BSTR</b> property associated with a list of values. The method also sets the property type to VT_BSTR and subtype to WIA_PROP_LIST (defined in the Microsoft Windows SDK documentation).


## -syntax


````
void SetValidValues(
   INT    index,
   BSTR   defaultValue,
   BSTR   currentValue,
   INT    numValues,
   BSTR   *pValues
);
````


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param defaultValue

Specifies the default setting of the property on the device.


### -param currentValue

Specifies the current setting of the property on the device.


### -param validFlags






#### - numValues

Specifies the number of values in the property list.


#### - pValues

Points to the first property in the property list. This pointer must remain valid until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a> method is called.


## -returns



This method does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::SetValidValues method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

