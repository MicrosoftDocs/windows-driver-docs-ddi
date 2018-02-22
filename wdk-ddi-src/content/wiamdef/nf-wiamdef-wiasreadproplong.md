---
UID: NF:wiamdef.wiasReadPropLong
title: wiasReadPropLong function
author: windows-driver-content
description: The wiasReadPropLong function retrieves a long integer property value from a WIA item.
old-location: image\wiasreadproplong.htm
old-project: Image
ms.assetid: 77fc58fd-1bcf-4a68-b083-fa2bfa3ac312
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: wiasReadPropLong function [Imaging Devices], image.wiasreadproplong, wiasFncs_a60071a3-6ae9-431d-8d8b-a964547e9770.xml, wiasReadPropLong, wiamdef/wiasReadPropLong
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
-	wiasReadPropLong
product: Windows
targetos: Windows
req.typenames: "*PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasReadPropLong function


## -description


The <b>wiasReadPropLong </b>function retrieves a long integer property value from a WIA item.


## -syntax


````
HRESULT _stdcall wiasReadPropLong(
  _In_      BYTE   *pWiasContext,
            PROPID propid,
  _Out_     LONG   *plVal,
  _Out_opt_ LONG   *plValOld,
            BOOL   bMustExist
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param plVal [out]

Pointer to a memory location that receives the value of the property.


### -param plValOld [out, optional]

Pointer to a memory location that receives the property's previous value. If this information is not needed, set this parameter to <b>NULL</b>.


### -param bMustExist

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist, if set to <b>FALSE</b>, the property does not have to exist.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropstr.md">wiasReadPropStr</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropfloat.md">wiasReadPropFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropstr.md">wiasReadPropStr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiasReadPropLong function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

