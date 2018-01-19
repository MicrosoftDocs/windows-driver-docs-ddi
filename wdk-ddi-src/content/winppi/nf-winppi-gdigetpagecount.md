---
UID: NF:winppi.GdiGetPageCount
title: GdiGetPageCount function
author: windows-driver-content
description: The GdiGetPageCount function returns the number of pages in a print job.
old-location: print\gdigetpagecount.htm
old-project: print
ms.assetid: 0a101b59-c610-4158-97a8-002222a94309
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: GdiGetPageCount
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
req.alt-api: GdiGetPageCount
req.alt-loc: Gdi32.dll,Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll,GDI32Full.dll
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
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# GdiGetPageCount function



## -description
The <b>GdiGetPageCount</b> function returns the number of pages in a print job.



## -syntax

````
DWORD GdiGetPageCount(
   HANDLE SpoolFileHandle
);
````


## -parameters

### -param SpoolFileHandle 

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## -returns
If the operation succeeds, the function returns the number of pages in the current print job. Otherwise the function returns zero.


## -remarks
The <b>GdiGetPageCount</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.
<p class="note">Usually, a better method for determining the page count is to count the number of calls made to <a href="..\winppi\nf-winppi-gdigetpagehandle.md">GdiGetPageHandle</a>.

For additional information about this set of functions, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.</p>