---
UID: NF:wiamdef.wiasWritePropBin
title: wiasWritePropBin function
author: windows-driver-content
description: The wiasWritePropBin function writes a single binary-data property value to a WIA item.
old-location: image\wiaswritepropbin.htm
old-project: image
ms.assetid: 953a43dd-1cab-442b-9d77-f310805166ee
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaswritepropbin, wiamdef/wiasWritePropBin, wiasFncs_fa38d5cc-94dd-4a1f-9e24-e12c42ce0429.xml, wiasWritePropBin, wiasWritePropBin function [Imaging Devices]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wiaservc.dll
api_name:
-	wiasWritePropBin
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
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

<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>



<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>



 

 


