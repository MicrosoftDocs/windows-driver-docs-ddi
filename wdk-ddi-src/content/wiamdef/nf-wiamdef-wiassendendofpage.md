---
UID: NF:wiamdef.wiasSendEndOfPage
title: wiasSendEndOfPage function
author: windows-driver-content
description: The wiasSendEndOfPage function calls the client callback routine during a data transfer, sending the current total page count.
old-location: image\wiassendendofpage.htm
old-project: image
ms.assetid: 107cd468-bc39-4672-9356-e5329b36277b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasFncs_c8a81130-c832-40d8-8a62-619d04d8d3dc.xml, wiasSendEndOfPage function [Imaging Devices], wiamdef/wiasSendEndOfPage, wiasSendEndOfPage, image.wiassendendofpage
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
-	wiasSendEndOfPage
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasSendEndOfPage function


## -description


The <b>wiasSendEndOfPage </b>function calls the client callback routine during a data transfer, sending the current total page count.


## -syntax


````
HRESULT _stdcall wiasSendEndOfPage(
  _In_    BYTE                      *pWiasContext,
          LONG                      lPageCount,
  _Inout_ PMINIDRV_TRANSFER_CONTEXT pmdtc
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param lPageCount

Specifies the total page count. 


### -param pmdtc [in, out]

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSendEndOfPage function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

