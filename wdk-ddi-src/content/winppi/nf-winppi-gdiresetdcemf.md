---
UID: NF:winppi.GdiResetDCEMF
title: GdiResetDCEMF function (winppi.h)
description: The GdiResetDCEMF function resets a printer's device context during playback of a spooled EMF print job.
old-location: print\gdiresetdcemf.htm
tech.root: print
ms.assetid: ea97cc22-6057-427d-90c1-4f23ced932aa
ms.date: 04/20/2018
ms.keywords: GdiResetDCEMF, GdiResetDCEMF function [Print Devices], gdifnc_ff066b35-7062-430e-a8b9-bbdef46494a6.xml, print.gdiresetdcemf, winppi/GdiResetDCEMF
ms.topic: function
f1_keywords:
 - "winppi/GdiResetDCEMF"
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
- GdiResetDCEMF
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiResetDCEMF function


## -description


The <b>GdiResetDCEMF</b> function resets a printer's device context during playback of a spooled EMF print job.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetspoolfilehandle">GdiGetSpoolFileHandle</a>.


### -param pCurrDM

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure, obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetdevmodeforpage">GdiGetDevmodeForPage</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.




## -remarks



The <b>GdiResetDCEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

Print processors must call <b>GdiResetDCEMF</b> whenever it is necessary to reset the printer's device context. The function must be called whenever the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winppi/nf-winppi-gdigetdevmodeforpage">GdiGetDevmodeForPage</a> function indicates that the current document page's <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure is not identical to that of the previous document page.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.



