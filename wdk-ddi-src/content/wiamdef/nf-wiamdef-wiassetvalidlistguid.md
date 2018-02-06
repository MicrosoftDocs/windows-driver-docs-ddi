---
UID: NF:wiamdef.wiasSetValidListGuid
title: wiasSetValidListGuid function
author: windows-driver-content
description: The wiasSetValidListGuid function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.
old-location: image\wiassetvalidlistguid.htm
old-project: image
ms.assetid: ab8276d4-4838-4bfc-8952-8712435eab41
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasSetValidListGuid function [Imaging Devices], wiasFncs_eade05c7-20bd-480d-aa50-0216575ce856.xml, wiamdef/wiasSetValidListGuid, wiasSetValidListGuid, image.wiassetvalidlistguid
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
-	wiasSetValidListGuid
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasSetValidListGuid function


## -description


The <b>wiasSetValidListGuid </b>function sets valid values for a WIA_PROP_LIST property of type VT_CLSID.


## -syntax


````
HRESULT _stdcall wiasSetValidListGuid(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulCount,
       GUID   gNom,
  _In_ GUID   *pgValues
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the identifier of the property to be updated.


### -param ulCount

Specifies the number of items in the <i>pgValues</i> array.


### -param guidNom

TBD


### -param pguidValues

TBD



#### - gNom

Specifies the property's nominal value.


#### - pgValues [in]

Pointer to the first element of an array of valid property values.


## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md">wiasSetValidRangeLong</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md">wiasSetValidListFloat</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidflag.md">wiasSetValidFlag</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md">wiasSetValidListLong</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md">wiasSetValidRangeFloat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidListGuid function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

