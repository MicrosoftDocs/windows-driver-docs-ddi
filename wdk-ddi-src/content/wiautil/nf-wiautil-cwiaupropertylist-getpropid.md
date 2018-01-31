---
UID: NF:wiautil.CWiauPropertyList.GetPropId
title: CWiauPropertyList::GetPropId method
author: windows-driver-content
description: The CWiauPropertyList::GetPropId method finds the property ID for a property, given its index in the property list.
old-location: image\cwiaupropertylist_getpropid.htm
old-project: image
ms.assetid: a06de368-71a1-49f1-a948-1b69ca359fb6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList::GetPropId, image.cwiaupropertylist_getpropid, wiauFncs_3463736c-9dd0-4b87-b427-b19a0daf0df9.xml, GetPropId method [Imaging Devices], wiautil/CWiauPropertyList::GetPropId, CWiauPropertyList interface [Imaging Devices], GetPropId method, GetPropId method [Imaging Devices], CWiauPropertyList interface, GetPropId
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
-	CWiauPropertyList.GetPropId
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::GetPropId method


## -description


The <b>CWiauPropertyList::GetPropId</b> method finds the property ID for a property, given its index in the property list.


## -syntax


````
PROPID GetPropId(
   INT  index
);
````


## -parameters




#### - index

Specifies the index of the property within the property list.


## -returns


The <b>CWiauPropertyList::GetPropId</b> method returns the property ID for the property.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540400">CWiauPropertyList::LookupPropId</a>

<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::GetPropId method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

