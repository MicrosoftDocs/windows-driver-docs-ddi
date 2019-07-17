---
UID: NF:winppi.GdiGetDC
title: GdiGetDC function (winppi.h)
description: The GdiGetDC function returns a handle to a printer's device context.
old-location: print\gdigetdc.htm
tech.root: print
ms.assetid: f8aacb6d-4e8a-4fdb-902c-3d0efbc40f08
ms.date: 04/20/2018
ms.keywords: GdiGetDC, GdiGetDC function [Print Devices], gdifnc_4129439c-9cb6-46d3-8659-d12438841bb5.xml, print.gdigetdc, winppi/GdiGetDC
ms.topic: function
f1_keywords:
 - "winppi/GdiGetDC"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
- GDI32Full.dll
api_name:
- GdiGetDC
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiGetDC function


## -description


The <b>GdiGetDC</b> function returns a handle to a printer's device context.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns a device context handle. Otherwise the function returns <b>NULL</b>.




## -remarks



The <b>GdiGetDC</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

A print processor can call <b>GdiGetDC</b> to obtain a printer's device context handle anytime after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>. The print processor can use the context handle to call Win32 device context functions, in order to perform such operations as applying transformations on the print image.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.



