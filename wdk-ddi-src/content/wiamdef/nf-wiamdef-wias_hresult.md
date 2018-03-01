---
UID: NF:wiamdef.WIAS_HRESULT
title: WIAS_HRESULT macro
author: windows-driver-content
description: The WIAS_HRESULT macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_hresult.htm
old-project: image
ms.assetid: e340eb98-34d4-49e7-92cd-4f57d8b6efb8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWiaLog_3b27b46f-be2e-4fdb-ba65-32fe41c71142.xml, WIAS_HRESULT, WIAS_HRESULT macro [Imaging Devices], image.wias_hresult, wiamdef/WIAS_HRESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
req.lib: wiamdef.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiamdef.h
api_name:
-	WIAS_HRESULT
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# WIAS_HRESULT macro


## -description


The WIAS_HRESULT macro writes a diagnostic message to the <i>Wiatrace.log</i> file.


## -syntax


````
HRESULT WIAS_HRESULT(
   HINSTANCE hInstance,
   HRESULT   hr
);
````


## -parameters




### -param x

TBD






#### - hInstance

Handle to the calling driver. 


#### - hr

Specifies the HRESULT value to be printed.


## -remarks



This macro is the recommended way to output HRESULTS on Windows Vista.




## -see-also

<a href="..\wiamdef\nf-wiamdef-wias_assert.md">WIAS_ASSERT</a>



<a href="..\wiamdef\nf-wiamdef-wias_error.md">WIAS_ERROR</a>



<a href="..\wiamdef\nf-wiamdef-wias_trace.md">WIAS_TRACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_HRESULT macro%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

