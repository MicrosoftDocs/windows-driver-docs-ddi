---
UID: NF:winppi.GdiGetPageHandle
title: GdiGetPageHandle function
author: windows-driver-content
description: The GdiGetPageHandle function returns a handle to the specified page within a print job.
old-location: print\gdigetpagehandle.htm
old-project: print
ms.assetid: 7eaed9d2-20fa-4cf1-b924-fbe1443535e9
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: GdiGetPageHandle, GdiGetPageHandle function [Print Devices], winppi/GdiGetPageHandle, print.gdigetpagehandle, gdifnc_3a8cdbd2-c73f-4b24-b984-9237b20327e1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winppi.h
req.include-header: Winppi.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Gdi32.Lib
req.dll: Gdi32.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
-	GDI32Full.dll
apiname:
-	GdiGetPageHandle
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# GdiGetPageHandle function


## -description


The <b>GdiGetPageHandle</b> function returns a handle to the specified page within a print job.


## -syntax


````
HANDLE GdiGetPageHandle(
   HANDLE  SpoolFileHandle,
   DWORD   Page,
   LPDWORD pdwPageType
);
````


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


### -param Page

Caller-supplied page number.


### -param pdwPageType

Caller-supplied pointer to a location that receives the page type. The possible page types are shown in the following table:

<table>
<tr>
<th>Page Type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
EMF_PP_FORM

</td>
<td>
The page is a form or has a watermark. (Not currently supported.)

</td>
</tr>
<tr>
<td>
EMF_PP_NORMAL

</td>
<td>
The page is a normal page.

</td>
</tr>
</table>
 


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiGetPageHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

Print processors must obtain a page handle before calling <a href="..\winppi\nf-winppi-gdiplaypageemf.md">GdiPlayPageEMF</a> to draw a page. If a Page value is specified that is too large, the function returns ERROR_NO_MORE_ITEMS.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.



