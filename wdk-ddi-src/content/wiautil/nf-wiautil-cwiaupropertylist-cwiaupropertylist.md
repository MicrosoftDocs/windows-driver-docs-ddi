---
UID: NF:wiautil.CWiauPropertyList.CWiauPropertyList
title: CWiauPropertyList::CWiauPropertyList method
author: windows-driver-content
description: The CWiauPropertyList::CWiauPropertyList method is the constructor for the CWiauPropertyList class.
old-location: image\cwiaupropertylist_cwiaupropertylist.htm
old-project: image
ms.assetid: 5e493d3c-81b6-4db5-a550-c86eadf5a723
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], CWiauPropertyList method, CWiauPropertyList method [Imaging Devices], CWiauPropertyList method [Imaging Devices], CWiauPropertyList interface, CWiauPropertyList,CWiauPropertyList.CWiauPropertyList, CWiauPropertyList::CWiauPropertyList, L, P, W, a, e, i, image.cwiaupropertylist_cwiaupropertylist, o, p, r, s, t, u, wiauFncs_834023ef-b425-4469-a5e7-c127fd5acf2a.xml, wiautil/CWiauPropertyList::CWiauPropertyList, y"
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
-	CWiauPropertyList.CWiauPropertyList
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::CWiauPropertyList method


## -description


The <b>CWiauPropertyList::CWiauPropertyList</b> method is the constructor for the <b>CWiauPropertyList</b> class.


## -syntax


````
void CWiauPropertyList();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



The <b>CWiauPropertyList</b> constructor initializes all data members of a property list object to either <b>NULL</b> or zero. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a> method to reserve memory for properties. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a> method once per property to add it to the property list object.




## -see-also

<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540472">CWiauPropertyList::~CWiauPropertyList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540391">CWiauPropertyList::DefineProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540396">CWiauPropertyList::Init</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::CWiauPropertyList method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

