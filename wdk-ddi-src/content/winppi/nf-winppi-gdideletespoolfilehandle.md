---
UID: NF:winppi.GdiDeleteSpoolFileHandle
title: GdiDeleteSpoolFileHandle function (winppi.h)
description: The GdiDeleteSpoolFileHandle function releases a spool file handle.
old-location: print\gdideletespoolfilehandle.htm
tech.root: print
ms.assetid: ff22498e-404f-42f6-82fd-f0178f6c7789
ms.date: 04/20/2018
keywords: ["GdiDeleteSpoolFileHandle function"]
ms.keywords: GdiDeleteSpoolFileHandle, GdiDeleteSpoolFileHandle function [Print Devices], gdifnc_76c1c0cf-2a48-44eb-9b48-1d0a5bf4548b.xml, print.gdideletespoolfilehandle, winppi/GdiDeleteSpoolFileHandle
f1_keywords:
 - "winppi/GdiDeleteSpoolFileHandle"
 - "GdiDeleteSpoolFileHandle"
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
req.lib: Gdi32.lib
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
- GdiDeleteSpoolFileHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiDeleteSpoolFileHandle function


## -description


The <b>GdiDeleteSpoolFileHandle</b> function releases a spool file handle.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.




## -remarks



The <b>GdiDeleteSpoolFileHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

Print processors should call <b>GdiDeleteSpoolFileHandle</b> after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdienddocemf">GdiEndDocEMF</a>, when processing a print job's EMF data stream has been completed. The function calls ClosePrinter (described in the Microsoft Window SDK documentation) to close the printer connection.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>
 

 

