---
UID: NF:wiamdef.wiasReadPropFloat
title: wiasReadPropFloat function
author: windows-driver-content
description: The wiasReadPropFloat function retrieves a floating-point property value from a WIA item.
old-location: image\wiasreadpropfloat.htm
old-project: image
ms.assetid: 042ef9d9-a980-41eb-a396-e03658ea072a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.wiasreadpropfloat, wiasReadPropFloat, wiasReadPropFloat function [Imaging Devices], wiamdef/wiasReadPropFloat, wiasFncs_9b143e96-64a5-4de3-b40d-c542bc440dc0.xml
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
-	wiasReadPropFloat
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasReadPropFloat function


## -description


The <b>wiasReadPropFloat </b>function retrieves a floating-point property value from a WIA item.


## -syntax


````
HRESULT _stdcall wiasReadPropFloat(
  _In_      BYTE   *pWiasContext,
            PROPID propid,
  _Out_     FLOAT  *pfVal,
  _Out_opt_ FLOAT  *pfValOld,
            BOOL   bMustExist
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param pfVal [out]

Pointer to a memory location that receives the floating-point value of the property.


### -param pfValOld [out, optional]

Pointer to a memory location that receives the former floating-point value of the property. If this information is not needed, set this parameter to <b>NULL</b>.


### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, it does not have to exist.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropstr.md">wiasReadPropStr</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadproplong.md">wiasReadPropLong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasReadPropFloat function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

