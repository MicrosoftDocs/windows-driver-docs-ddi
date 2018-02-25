---
UID: NF:wiamindr_lh.IWiaDrvItem.GetItemFlags
title: IWiaDrvItem::GetItemFlags method
author: windows-driver-content
description: The IWiaDrvItem::GetItemFlags method gets the item flags of the current IWiaDrvItem item.
old-location: image\iwiadrvitem_getitemflags.htm
old-project: image
ms.assetid: 47358d69-ef45-4cac-8187-72c354912c4e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, D, DrvItem_6fcac1f5-c754-4158-a1a0-61efe0d3913c.xml, F, G, GetItemFlags method [Imaging Devices], GetItemFlags method [Imaging Devices], IWiaDrvItem interface, GetItemFlags,IWiaDrvItem.GetItemFlags, I, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], GetItemFlags method, IWiaDrvItem::GetItemFlags, W, a, e, g, i, image.iwiadrvitem_getitemflags, l, m, r, s, t, v, wiamindr_lh/IWiaDrvItem::GetItemFlags"
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
-	IWiaDrvItem.GetItemFlags
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem::GetItemFlags method


## -description


The <b>IWiaDrvItem::GetItemFlags</b> method gets the item flags of the current <b>IWiaDrvItem</b> item.


## -syntax


````
HRESULT GetItemFlags(
  [out] LONG *plFlags
);
````


## -parameters




### -param __MIDL__IWiaDrvItem0000






#### - plFlags [out]

Points to a memory location that will receive the item flags.


## -returns



If the method succeeds, it places the item flag values in the location pointed to by <i>plFlags</i> and returns S_OK. If the pointer <i>plFlags</i> is invalid, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.




## -remarks



The method places the current <b>IWiaDrvItem</b> item's flag values in the location pointed to by <i>pIFlags</i>. The item's flag values were set when the item was created by the driver services library function <a href="..\wiamdef\nf-wiamdef-wiascreatedrvitem.md">wiasCreateDrvItem</a>.




## -see-also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>



<a href="..\wiamdef\nf-wiamdef-wiascreatedrvitem.md">wiasCreateDrvItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetItemFlags method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

