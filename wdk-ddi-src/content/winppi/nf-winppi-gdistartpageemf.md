---
UID: NF:winppi.GdiStartPageEMF
title: GdiStartPageEMF function
author: windows-driver-content
description: The GdiStartPageEMF function performs initialization operations for a physical page of an EMF-formatted print job.
old-location: print\gdistartpageemf.htm
old-project: print
ms.assetid: 963c809f-da89-4f27-ba8b-3de8cdcec179
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GdiStartPageEMF, GdiStartPageEMF function [Print Devices], gdifnc_fbb09921-04b5-49e2-b8a7-fe23657a0f4f.xml, print.gdistartpageemf, winppi/GdiStartPageEMF
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
-	GDI32Full.dll
api_name:
-	GdiStartPageEMF
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# GdiStartPageEMF function


## -description


The <b>GdiStartPageEMF</b> function performs initialization operations for a physical page of an EMF-formatted print job.


## -syntax


````
BOOL GdiStartPageEMF(
   HANDLE SpoolFileHandle
);
````


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiStartPageEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

A print processor must call the <b>GdiStartPageEMF</b> function each time a new physical page is to be created. It can then call <a href="..\winppi\nf-winppi-gdiplaypageemf.md">GdiPlayPageEMF</a> for each document page that is to be placed on the physical page.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.




## -see-also

<a href="..\winppi\nf-winppi-gdiendpageemf.md">GdiEndPageEMF</a>



 

 


