---
UID: NF:winppi.GdiStartDocEMF
title: GdiStartDocEMF function
author: windows-driver-content
description: The GdiStartDocEMF function performs initialization operations for an EMF-formatted print job.
old-location: print\gdistartdocemf.htm
tech.root: print
ms.assetid: aca4534a-871e-4d86-b329-cb4f84611a29
ms.date: 4/20/2018
ms.keywords: GdiStartDocEMF, GdiStartDocEMF function [Print Devices], gdifnc_11790088-e5fa-4817-a7d7-79c654814062.xml, print.gdistartdocemf, winppi/GdiStartDocEMF
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
-	GdiStartDocEMF
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiStartDocEMF function


## -description


The <b>GdiStartDocEMF</b> function performs initialization operations for an EMF-formatted print job.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549517">GdiGetSpoolFileHandle</a>.


### -param pDocInfo

Caller-supplied pointer to a DOCINFOW structure (described in the Microsoft Window SDK documentation).


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiStartDocEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560724">PrintDocumentOnPrintProcessor</a> function.

The function performs initializations that must take place before a print job's EMF records can be played. The function calls the spooler's <b>StartDoc</b> function (described in the Window SDK documentation), which in turn calls the printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556296">DrvStartDoc</a> function.

The print processor must set the <b>lpszOutput</b> member of the DOCINFOW structure to the output file name contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560988">PRINTPROCESSOROPENDATA</a> structure, previously received by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559604">OpenPrintProcessor</a> function.

The print processor must set the <b>lpszDocName</b> member of the DOCINFOW structure to the document name pointer, previously received by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560724">PrintDocumentOnPrintProcessor</a> function.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549463">GdiEndDocEMF</a>
 

 

