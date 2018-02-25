---
UID: NF:wiamdef.wiasWritePropFloat
title: wiasWritePropFloat function
author: windows-driver-content
description: The wiasWritePropFloat function writes a single floating-point property value to a WIA item.
old-location: image\wiaswritepropfloat.htm
old-project: image
ms.assetid: 097cd455-018e-46ef-8b8f-8eae7ea3eaff
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , F, P, W, a, e, i, image.wiaswritepropfloat, l, o, p, r, s, t, w, wiamdef/wiasWritePropFloat, wiasFncs_49539474-675e-420d-b7a4-67f147017975.xml, wiasWritePropFloat, wiasWritePropFloat function [Imaging Devices]"
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
-	wiasWritePropFloat
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasWritePropFloat function


## -description


The <b>wiasWritePropFloat </b>function writes a single floating-point property value to a WIA item.


## -syntax


````
HRESULT _stdcall wiasWritePropFloat(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       float  fVal
);
````


## -parameters




### -param pWiasContext [in]

A Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param fVal

Specifies the floating-point property value to write to the item.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>



<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>



<a href="..\wiamdef\nf-wiamdef-wiaswritepropbin.md">wiasWritePropBin</a>



<a href="..\wiamdef\nf-wiamdef-wiasreadpropfloat.md">wiasReadPropFloat</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWritePropFloat function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

