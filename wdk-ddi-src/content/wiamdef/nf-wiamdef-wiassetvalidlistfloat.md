---
UID: NF:wiamdef.wiasSetValidListFloat
title: wiasSetValidListFloat function
author: windows-driver-content
description: The wiasSetValidListFloat function sets valid values for a WIA_PROP_LIST property of type VT_R4.
old-location: image\wiassetvalidlistfloat.htm
old-project: image
ms.assetid: e1a833aa-fc8b-4506-aba8-ba6dc9a375ba
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiassetvalidlistfloat, wiamdef/wiasSetValidListFloat, wiasFncs_ef1aa836-f63d-43e8-8378-22d37fbdc3a2.xml, wiasSetValidListFloat, wiasSetValidListFloat function [Imaging Devices]
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
-	wiasSetValidListFloat
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasSetValidListFloat function


## -description


The <b>wiasSetValidListFloat </b>function sets valid values for a WIA_PROP_LIST property of type VT_R4.


## -syntax


````
HRESULT _stdcall wiasSetValidListFloat(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulCount,
       FLOAT  fNom,
  _In_ FLOAT  *pfValues
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param ulCount

Specifies the number of items in the <i>plValues</i> array.


### -param fNom

Specifies the property's nominal value.


### -param pfValues [in]

Pointer to the first element of an array of valid property values.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md">wiasSetValidRangeFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md">wiasSetValidRangeLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md">wiasSetValidListLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidflag.md">wiasSetValidFlag</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md">wiasSetValidListGuid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidListFloat function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

