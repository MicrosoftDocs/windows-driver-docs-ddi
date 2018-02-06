---
UID: NF:winppi.GdiGetDC
title: GdiGetDC function
author: windows-driver-content
description: The GdiGetDC function returns a handle to a printer's device context.
old-location: print\gdigetdc.htm
old-project: print
ms.assetid: f8aacb6d-4e8a-4fdb-902c-3d0efbc40f08
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.gdigetdc, winppi/GdiGetDC, GdiGetDC, gdifnc_4129439c-9cb6-46d3-8659-d12438841bb5.xml, GdiGetDC function [Print Devices]
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
-	GdiGetDC
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME"
req.product: Windows 10 or later.
---

# GdiGetDC function


## -description


The <b>GdiGetDC</b> function returns a handle to a printer's device context.


## -syntax


````
HDC GdiGetDC(
   HANDLE SpoolFileHandle
);
````


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## -returns


If the operation succeeds, the function returns a device context handle. Otherwise the function returns <b>NULL</b>.



## -remarks


The <b>GdiGetDC</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

A print processor can call <b>GdiGetDC</b> to obtain a printer's device context handle anytime after calling <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>. The print processor can use the context handle to call Win32 device context functions, in order to perform such operations as applying transformations on the print image.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.


