---
UID: NF:wiamdef.wiasPrintDebugHResult
title: wiasPrintDebugHResult function
author: windows-driver-content
description: The wiasPrintDebugHResult function is obsolete for Windows XP and later, and is no longer supported. Use the WIAS_LHRESULT macro instead.This function prints an HRESULT string on the Device Manager debug console.
old-location: image\wiasprintdebughresult.htm
old-project: image
ms.assetid: f9dc5379-0efa-4743-9460-bfb16945768b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasFncs_932e688a-da37-4a53-91ff-f0c0abca4f98.xml, wiasPrintDebugHResult, wiasPrintDebugHResult function [Imaging Devices], image.wiasprintdebughresult, wiamdef/wiasPrintDebugHResult
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
-	wiasPrintDebugHResult
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# wiasPrintDebugHResult function


## -description


The <b>wiasPrintDebugHResult</b> function is <b>obsolete</b> for Windows XP and later, and is no longer supported. Use the <a href="..\wiamdef\nf-wiamdef-wias_lhresult.md">WIAS_LHRESULT</a> macro instead.

This function prints an HRESULT string on the Device Manager debug console.


## -syntax


````
VOID __stdcall wiasPrintDebugHResult(
   HINSTANCE  hInstance,
   HRESULT    hr
);
````


## -parameters




### -param hInstance

Is the module handle of the calling module.


### -param hr

Specifies the HRESULT to be printed.


## -returns


On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).



## -see-also

<a href="..\wiamdef\nf-wiamdef-wias_lhresult.md">WIAS_LHRESULT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasPrintDebugHResult function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

