---
UID: NF:wiamindr_lh.IWiaDrvItem.GetItemName
title: IWiaDrvItem::GetItemName method
author: windows-driver-content
description: The IWiaDrvItem::GetItemName method gets the current IWiaDrvItem item name, not including path information.
old-location: image\iwiadrvitem_getitemname.htm
old-project: image
ms.assetid: 1e731975-13f8-4b5d-93de-714f62e9591f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetItemName method [Imaging Devices], IWiaDrvItem interface, GetItemName method [Imaging Devices], DrvItem_18b6c67e-9d95-45d4-844f-90fcb5c277bd.xml, wiamindr_lh/IWiaDrvItem::GetItemName, IWiaDrvItem::GetItemName, GetItemName, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], GetItemName method, image.iwiadrvitem_getitemname
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
-	IWiaDrvItem.GetItemName
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem::GetItemName method


## -description


The <b>IWiaDrvItem::GetItemName</b> method gets the current <b>IWiaDrvItem</b> item name, not including path information.


## -syntax


````
HRESULT GetItemName(
  [out, optional] BSTR *pbstrItemName
);
````


## -parameters




### -param __MIDL__IWiaDrvItem0003





#### - pbstrItemName [out, optional]

Points to a memory location that will receive the address of the string containing the item name. 


## -returns


If the method succeeds, it stores a pointer to the item's name (path information is not included) in <i>pbstrItemName</i> and returns S_OK. If the method fails to allocate the string due to insufficient memory, it returns E_OUTOFMEMORY. If the parameter <i>pbstrItemName</i> is invalid, the method returns E_INVALIDARG.If the method fails for another reason, it returns a standard COM error code.



## -remarks


If there is enough memory available, the method allocates a string containing the current item's name, excluding path information. The method returns a pointer to the string in <i>pbstrItemName</i>. The minidriver must deallocate the memory used by the string by calling the <b>SysFreeString</b> function, which is documented in the Microsoft Windows SDK. 



## -see-also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543881">IWiaDrvItem::GetFullItemName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetItemName method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

