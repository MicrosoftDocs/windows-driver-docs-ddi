---
UID: NF:winppi.GdiGetPageCount
title: GdiGetPageCount function (winppi.h)
description: The GdiGetPageCount function returns the number of pages in a print job.
old-location: print\gdigetpagecount.htm
tech.root: print
ms.assetid: 0a101b59-c610-4158-97a8-002222a94309
ms.date: 04/20/2018
keywords: ["GdiGetPageCount function"]
ms.keywords: GdiGetPageCount, GdiGetPageCount function [Print Devices], gdifnc_f34bbc65-29f2-47b1-aec3-523af01a804c.xml, print.gdigetpagecount, winppi/GdiGetPageCount
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GdiGetPageCount
 - winppi/GdiGetPageCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
 - GDI32Full.dll
api_name:
 - GdiGetPageCount
---

# GdiGetPageCount function


## -description

The <b>GdiGetPageCount</b> function returns the number of pages in a print job.

## -parameters

### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.

## -returns

If the operation succeeds, the function returns the number of pages in the current print job. Otherwise the function returns zero.

## -remarks

The <b>GdiGetPageCount</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

<div class="alert"><b>Note</b>  The <b>GdiGetPageCount</b> function does not return until all pages have been spooled, even if the print server administrator has specified that print jobs should be printed during spooling. Therefore, this function should not be used unless it is necessary to obtain the total page count before document processing can begin, such as for printing pages in reverse order.<p class="note">Usually, a better method for determining the page count is to count the number of calls made to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetpagehandle">GdiGetPageHandle</a>.

</div>
<div> </div>
For additional information about this set of functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.

