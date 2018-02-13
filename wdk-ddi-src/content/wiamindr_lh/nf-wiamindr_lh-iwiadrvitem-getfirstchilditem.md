---
UID: NF:wiamindr_lh.IWiaDrvItem.GetFirstChildItem
title: IWiaDrvItem::GetFirstChildItem method
author: windows-driver-content
description: The IWiaDrvItem::GetFirstChildItem method gets the first child item in an IWiaDrvItem folder item.
old-location: image\iwiadrvitem_getfirstchilditem.htm
old-project: image
ms.assetid: 2e580a57-03cb-4ff4-b3c6-0b5ef17b4ccb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetFirstChildItem method [Imaging Devices], IWiaDrvItem interface, IWiaDrvItem::GetFirstChildItem, GetFirstChildItem, IWiaDrvItem, GetFirstChildItem method [Imaging Devices], image.iwiadrvitem_getfirstchilditem, DrvItem_0ee76640-f07a-4b25-9955-230122a2a662.xml, IWiaDrvItem interface [Imaging Devices], GetFirstChildItem method, wiamindr_lh/IWiaDrvItem::GetFirstChildItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wiamindr_lh.h
apiname:
-	IWiaDrvItem.GetFirstChildItem
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem::GetFirstChildItem method


## -description


The <b>IWiaDrvItem::GetFirstChildItem</b> method gets the first child item in an <b>IWiaDrvItem</b> folder item.


## -syntax


````
HRESULT GetFirstChildItem(
  [out, optional] IWiaDrvItem **ppIChildItem
);
````


## -parameters




### -param __MIDL__IWiaDrvItem0013






#### - ppIChildItem [out, optional]

Points to a memory location that will receive the address of an <b>IWiaDrvItem</b> child item.


## -returns



If the method succeeds, it stores a pointer to the first child item in <i>ppIChildItem</i> and returns S_OK. If a child item cannot be found, the method returns S_FALSE. If the item being searched is not a folder, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.




## -remarks



Minidrivers typically use this method to retrieve the first child item in a driver item folder. The item being searched must be a folder item.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543892">IWiaDrvItem::GetParentItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543889">IWiaDrvItem::GetNextSiblingItem</a>



<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetFirstChildItem method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

