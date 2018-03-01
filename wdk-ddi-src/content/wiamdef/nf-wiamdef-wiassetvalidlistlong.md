---
UID: NF:wiamdef.wiasSetValidListLong
title: wiasSetValidListLong function
author: windows-driver-content
description: The wiasSetValidListLong function sets the valid values for a WIA_PROP_LIST property of type VT_I4.
old-location: image\wiassetvalidlistlong.htm
old-project: image
ms.assetid: a8c3d2fa-7c21-4c6a-b395-af28029c9c15
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiassetvalidlistlong, wiamdef/wiasSetValidListLong, wiasFncs_0ccc4e24-3b86-426e-94c6-7c8bb19811f8.xml, wiasSetValidListLong, wiasSetValidListLong function [Imaging Devices]
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
-	wiasSetValidListLong
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasSetValidListLong function


## -description


The <b>wiasSetValidListLong </b>function sets the valid values for a WIA_PROP_LIST property of type VT_I4.


## -syntax


````
HRESULT _stdcall wiasSetValidListLong(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulCount,
       LONG   lNom,
       LONG   *plValues
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param ulCount

Specifies the number of items in the <i>plValues</i> array.


### -param lNom

Specifies the property's nominal value.


### -param plValues

Pointer to the first element of an array of valid property values.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiassetvalidflag.md">wiasSetValidFlag</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md">wiasSetValidListGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md">wiasSetValidRangeLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md">wiasSetValidRangeFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md">wiasSetValidListFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidListLong function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

