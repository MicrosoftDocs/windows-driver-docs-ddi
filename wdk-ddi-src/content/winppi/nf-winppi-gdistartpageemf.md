---
UID: NF:winppi.GdiStartPageEMF
title: GdiStartPageEMF function
author: windows-driver-content
description: The GdiStartPageEMF function performs initialization operations for a physical page of an EMF-formatted print job.
old-location: print\gdistartpageemf.htm
old-project: print
ms.assetid: 963c809f-da89-4f27-ba8b-3de8cdcec179
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winppi/GdiStartPageEMF, GdiStartPageEMF function [Print Devices], gdifnc_fbb09921-04b5-49e2-b8a7-fe23657a0f4f.xml, GdiStartPageEMF, print.gdistartpageemf
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
-	GdiStartPageEMF
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WPS_DEVICE_NAME, DOT11_WPS_DEVICE_NAME"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GdiStartPageEMF function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

