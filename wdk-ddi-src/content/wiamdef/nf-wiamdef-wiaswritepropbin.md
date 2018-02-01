---
UID: NF:wiamdef.wiasWritePropBin
title: wiasWritePropBin function
author: windows-driver-content
description: The wiasWritePropBin function writes a single binary-data property value to a WIA item.
old-location: image\wiaswritepropbin.htm
old-project: image
ms.assetid: 953a43dd-1cab-442b-9d77-f310805166ee
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasWritePropBin, wiasWritePropBin function [Imaging Devices], wiasFncs_fa38d5cc-94dd-4a1f-9e24-e12c42ce0429.xml, image.wiaswritepropbin, wiamdef/wiasWritePropBin
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
-	wiasWritePropBin
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasWritePropBin function


## -description


The <b>wiasWritePropBin </b>function writes a single binary-data property value to a WIA item.


## -syntax


````
HRESULT _stdcall wiasWritePropBin(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       LONG   cbVal,
  _In_ BYTE   *pbVal
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param cbVal

Specifies the total number of bytes to write to the item.


### -param pbVal [in]

Pointer to the first byte of an array of bytes to be written to the item.


## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>

<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWritePropBin function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

