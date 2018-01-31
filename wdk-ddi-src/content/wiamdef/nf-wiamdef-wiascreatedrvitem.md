---
UID: NF:wiamdef.wiasCreateDrvItem
title: wiasCreateDrvItem function
author: windows-driver-content
description: The wiasCreateDrvItem function creates an IWiaDrvItem Interface object.
old-location: image\wiascreatedrvitem.htm
old-project: image
ms.assetid: bc91133a-ae6a-447a-8519-65fbe2929521
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasCreateDrvItem function [Imaging Devices], wiamdef/wiasCreateDrvItem, wiasCreateDrvItem, wiasFncs_9bede31d-0ac0-4cc7-bdd5-7734e5f82dfc.xml, image.wiascreatedrvitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Wiaservc.dll
apiname:
-	wiasCreateDrvItem
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasCreateDrvItem function


## -description


The <b>wiasCreateDrvItem </b>function creates an <a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem Interface</a> object.


## -syntax


````
HRESULT _stdcall wiasCreateDrvItem(
          LONG        lObjectFlags,
          BSTR        bstrItemName,
          BSTR        bstrFullItemName,
  _Inout_ IWiaMiniDrv *pIMiniDrv,
          LONG        cbDevSpecContext,
  _Out_   BYTE        **ppDevSpecContext,
  _Out_   IWiaDrvItem **ppIWiaDrvItem
);
````


## -parameters




#### - lObjectFlags

Specifies the object item type, which must be WiaItemTypeFolder or WiaItemTypeFile (possibly the bitwise OR of these). These flags are described in the Microsoft Windows SDK documentation.


#### - bstrItemName

Specifies a string that contains the item name without path information.


#### - bstrFullItemName

Specifies a string that contains the item name with path information.


#### - pIMiniDrv [in, out]

Pointer to the <a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv Interface</a> of the current minidriver.


#### - cbDevSpecContext

Specifies the size in bytes of the device specific context.


#### - ppDevSpecContext [out]

Pointer to a memory location that receives the address of the device specific context. Set this to <b>NULL</b> if the information is not needed.


#### - ppIWiaDrvItem [out]

Pointer to a memory location that receives the address of an <a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem Interface</a> for the newly created <b>IWiaDrvItem</b> object.


## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).



## -remarks


This function creates and initializes an <a href="https://msdn.microsoft.com/1be2265b-7ae8-4935-9559-588b885526d4">IWiaDrvItem COM Interface</a> object with the specified name and attributes. It also creates a context for the <b>IWiaDrvItem</b> object. Minidrivers typically use this function to build a tree of device items.



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiascreatechildappitem.md">wiasCreateChildAppItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasCreateDrvItem function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

