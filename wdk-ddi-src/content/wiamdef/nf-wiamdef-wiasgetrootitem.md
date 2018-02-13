---
UID: NF:wiamdef.wiasGetRootItem
title: wiasGetRootItem function
author: windows-driver-content
description: The wiasGetRootItem function retrieves the root item context of a specified WIA item.
old-location: image\wiasgetrootitem.htm
old-project: image
ms.assetid: 09885782-2293-49a3-af48-6450dbc6a24e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasGetRootItem, image.wiasgetrootitem, wiamdef/wiasGetRootItem, wiasGetRootItem function [Imaging Devices], wiasFncs_4e991723-5462-456e-b56f-82a38e5cf556.xml
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
-	wiasGetRootItem
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasGetRootItem function


## -description


The <b>wiasGetRootItem</b> function retrieves the root item context of a specified WIA item.


## -syntax


````
HRESULT _stdcall wiasGetRootItem(
  _In_  BYTE *pWiasContext,
  _Out_ BYTE **ppWiasContext
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param ppWiasContext [out]

Pointer to a memory location that receives the address of the WIA item's root item context.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasgetdrvitem.md">wiasGetDrvItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasGetRootItem function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

