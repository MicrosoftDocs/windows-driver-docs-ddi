---
UID: NF:winppi.GdiEndDocEMF
title: GdiEndDocEMF function
author: windows-driver-content
description: The GdiEndDocEMF function ends EMF playback operations for an EMF-formatted print job.
old-location: print\gdienddocemf.htm
old-project: print
ms.assetid: e58403d4-aacc-4d22-98e5-86db1a69c54a
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: GdiEndDocEMF function [Print Devices], winppi/GdiEndDocEMF, print.gdienddocemf, gdifnc_632b9c31-c0c1-4447-8a0c-ac8fb6b5af55.xml, GdiEndDocEMF
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
-	GdiEndDocEMF
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# GdiEndDocEMF function


## -description


The <b>GdiEndDocEMF</b> function ends EMF playback operations for an EMF-formatted print job.


## -syntax


````
BOOL GdiEndDocEMF(
   HANDLE SpoolFileHandle
);
````


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.




## -remarks



The <b>GdiEndDocEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

The function performs operations that must be performed after a print job's EMF records have been played. The function calls the spooler's <b>EndDoc</b> function (described in the Microsoft Window SDK documentation), which in turn calls the printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556215">DrvEndDoc</a> function.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.




## -see-also

<a href="..\winppi\nf-winppi-gdistartdocemf.md">GdiStartDocEMF</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GdiEndDocEMF function%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

