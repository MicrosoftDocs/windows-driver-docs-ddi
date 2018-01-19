---
UID: NF:winppi.GdiResetDCEMF
title: GdiResetDCEMF function
author: windows-driver-content
description: The GdiResetDCEMF function resets a printer's device context during playback of a spooled EMF print job.
old-location: print\gdiresetdcemf.htm
old-project: print
ms.assetid: ea97cc22-6057-427d-90c1-4f23ced932aa
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: GdiResetDCEMF
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
req.alt-api: GdiResetDCEMF
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

# GdiResetDCEMF function



## -description
The <b>GdiResetDCEMF</b> function resets a printer's device context during playback of a spooled EMF print job.



## -syntax

````
BOOL GdiResetDCEMF(
   HANDLE    SpoolFileHandle,
   PDEVMODEW pCurrDM
);
````


## -parameters

### -param SpoolFileHandle 

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


### -param pCurrDM 

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetdevmodeforpage.md">GdiGetDevmodeForPage</a>.


## -returns
If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.


## -remarks
The <b>GdiResetDCEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

Print processors must call <b>GdiResetDCEMF</b> whenever it is necessary to reset the printer's device context. The function must be called whenever the <a href="..\winppi\nf-winppi-gdigetdevmodeforpage.md">GdiGetDevmodeForPage</a> function indicates that the current document page's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure is not identical to that of the previous document page.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.</p>