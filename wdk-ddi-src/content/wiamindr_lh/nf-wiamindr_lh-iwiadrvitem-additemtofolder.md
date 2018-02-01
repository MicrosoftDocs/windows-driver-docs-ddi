---
UID: NF:wiamindr_lh.IWiaDrvItem.AddItemToFolder
title: IWiaDrvItem::AddItemToFolder method
author: windows-driver-content
description: The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.
old-location: image\iwiadrvitem_additemtofolder.htm
old-project: image
ms.assetid: 3f1cd0bf-13ce-49bc-a48e-dc3d89f3c7d7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IWiaDrvItem interface [Imaging Devices], AddItemToFolder method, DrvItem_7979b3e5-dfd3-41bb-ae55-266cbb74866c.xml, AddItemToFolder method [Imaging Devices], IWiaDrvItem interface, IWiaDrvItem::AddItemToFolder, IWiaDrvItem, image.iwiadrvitem_additemtofolder, AddItemToFolder, AddItemToFolder method [Imaging Devices], wiamindr_lh/IWiaDrvItem::AddItemToFolder
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
-	IWiaDrvItem.AddItemToFolder
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem::AddItemToFolder method


## -description


The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.


## -syntax


````
HRESULT AddItemToFolder(
  [in, optional] IWiaDrvItem *pIParent
);
````


## -parameters




### -param __MIDL__IWiaDrvItem0004





#### - pIParent [in, optional]

Points to the IWiaDrvItem parent folder item.


## -returns


If the method succeeds, it returns S_OK. If the method fails because an invalid <i>pIParent</i> parameter is passed, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.



## -remarks


Minidrivers typically use the AddItemToFolder method to add an item to a parent folder item in a driver item tree. The parent folder item is pointed to by the parameter <i>pIParent</i>. The item pointed to by <i>pIParent</i> must be a folder.



## -see-also

<a href="https://msdn.microsoft.com/f800427e-d6b6-4f4c-aee7-4b2b0d0aa0c4">RemoveItemFromFolder</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::AddItemToFolder method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

