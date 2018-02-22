---
UID: NF:wiamdef.wiasSetValidRangeFloat
title: wiasSetValidRangeFloat function
author: windows-driver-content
description: The wiasSetValidRangeFloat function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_R4.
old-location: image\wiassetvalidrangefloat.htm
old-project: Image
ms.assetid: 66bc5e03-4cc2-4de3-b707-18ff7e0deb4b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: wiasSetValidRangeFloat, image.wiassetvalidrangefloat, wiasSetValidRangeFloat function [Imaging Devices], wiamdef/wiasSetValidRangeFloat, wiasFncs_d8eb35e4-e295-43cf-a457-5e6fac3f537d.xml
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
-	wiasSetValidRangeFloat
product: Windows
targetos: Windows
req.typenames: "*PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasSetValidRangeFloat function


## -description


The <b>wiasSetValidRangeFloat </b>function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_R4.


## -syntax


````
HRESULT _stdcall wiasSetValidRangeFloat(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       FLOAT  fMin,
       FLOAT  fNom,
       FLOAT  fMax,
       FLOAT  fStep
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param fMin

Specifies the minimum value of the valid range.


### -param fNom

Specifies the property's nominal value.


### -param fMax

Specifies the maximum value of the valid range.


### -param fStep

Specifies the increment between each valid value in the range.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md">wiasSetValidListGuid</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md">wiasSetValidListLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md">wiasSetValidListFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidflag.md">wiasSetValidFlag</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md">wiasSetValidRangeLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiasSetValidRangeFloat function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

