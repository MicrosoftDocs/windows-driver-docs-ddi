---
UID: NF:wiamdef.wiasWritePropGuid
title: wiasWritePropGuid function
author: windows-driver-content
description: The wiasWritePropGuid function writes a single GUID property value to a WIA item.
old-location: image\wiaswritepropguid.htm
old-project: image
ms.assetid: 1189fe8d-7b94-46ed-9090-bfe40f244e6a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasWritePropGuid, wiasFncs_2d4110e9-d2e5-47a2-8213-d221e77c527d.xml, wiamdef/wiasWritePropGuid, wiasWritePropGuid function [Imaging Devices], image.wiaswritepropguid
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
-	wiasWritePropGuid
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasWritePropGuid function


## -description


The <b>wiasWritePropGuid </b>function writes a single GUID property value to a WIA item.


## -syntax


````
HRESULT _stdcall wiasWritePropGuid(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       GUID   gVal
);
````


## -parameters




### -param pWiasContext [in]

Pointer to a WIA item context.


### -param propid

Specifies the property identifier.


### -param guidVal

TBD



#### - gVal

Specifies a GUID property value to write to the item.


## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).



## -see-also

<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>

<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropbin.md">wiasWritePropBin</a>

<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWritePropGuid function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

