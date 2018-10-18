---
UID: NF:winppi.GdiGetDevmodeForPage
title: GdiGetDevmodeForPage function
author: windows-driver-content
description: The GdiGetDevmodeForPage function returns DEVMODEW structures for the specified and previous pages of a print job.
old-location: print\gdigetdevmodeforpage.htm
tech.root: print
ms.assetid: 3410e8b1-820f-4892-8d26-d803e3f943da
ms.date: 4/20/2018
ms.keywords: GdiGetDevmodeForPage, GdiGetDevmodeForPage function [Print Devices], gdifnc_39ecbc8c-73fb-4e71-9df7-abdc4d8ccdcf.xml, print.gdigetdevmodeforpage, winppi/GdiGetDevmodeForPage
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
-	GdiGetDevmodeForPage
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiGetDevmodeForPage function


## -description


The <b>GdiGetDevmodeForPage</b> function returns <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structures for the specified and previous pages of a print job.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549517">GdiGetSpoolFileHandle</a>.


### -param dwPageNumber

Caller-supplied number of the page for which <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> contents are to be returned.


### -param pCurrDM

Caller-supplied location to receive a pointer to a DEVMODE structure for the page specified by <i>dwPageNumber</i>.


### -param pLastDM

Caller-supplied location to receive a pointer to a DEVMODE structure for the page previous to the one specified by <i>dwPageNumber</i>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise it returns <b>FALSE</b>.




## -remarks



The <b>GdiGetDevmodeForPage</b> function is exported by gdi32.dll for use within a print processor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560724">PrintDocumentOnPrintProcessor</a> function.

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549524">GdiPlayPageEMF</a> to execute a page's EMF instructions, a print processor must call <b>GdiGetDevmodeForPage</b> to determine if the DEVMODE structure associated with the page to be printed is the same as that of the last page printed. If the two returned DEVMODE structures are not identical, the print processor must perform the following steps, in order, before calling <b>GdiPlayPageEMF</b> for the page:

<ol>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549468">GdiEndPageEMF</a>.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549529">GdiResetDCEMF</a>, specifying the DEVMODE pointed to by <i>pCurrDM</i>.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549543">GdiStartPageEMF</a>.

</li>
</ol>
For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.



