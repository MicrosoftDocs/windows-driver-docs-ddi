---
UID: NF:wiautil.CWiauPropertyList.SetCurrentValue
title: CWiauPropertyList::SetCurrentValue method
author: windows-driver-content
description: The CWiauPropertyList::SetCurrentValue(BSTR) method sets the current value of a property of type BSTR, and sets its type to VT_BSTR.
old-location: image\cwiaupropertylist_setcurrentvalue_bstr_.htm
old-project: image
ms.assetid: 017ab648-ee62-47f5-abd3-f4eac4378b8a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], SetCurrentValue method, CWiauPropertyList::SetCurrentValue, L, P, S, SetCurrentValue method [Imaging Devices], SetCurrentValue method [Imaging Devices], CWiauPropertyList interface, SetCurrentValue,CWiauPropertyList.SetCurrentValue, V, W, a, e, i, image.cwiaupropertylist_setcurrentvalue_bstr_, l, n, o, p, r, s, t, u, wiauFncs_dfd640f7-63c2-41a6-adf3-589e87aa85cc.xml, wiautil/CWiauPropertyList::SetCurrentValue, y"
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
-	CWiauPropertyList.SetCurrentValue
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::SetCurrentValue method


## -description


The <b>CWiauPropertyList::SetCurrentValue(BSTR)</b> method sets the current value of a property of type <b>BSTR</b>, and sets its type to VT_BSTR.


## -syntax


````
void SetCurrentValue(
   INT    index,
   BSTR   value
);
````


## -parameters




### -param index

Specifies the property index. Set this parameter to the value in *<i>pIdx</i> when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method returns.


### -param value

Pointer to a memory location containing the value that is written to the device property in the property list. This pointer must remain valid until the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a> method is called.


## -returns



This method does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540403">CWiauPropertyList::SendToWia</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::SetCurrentValue method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

