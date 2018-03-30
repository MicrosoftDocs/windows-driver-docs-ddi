---
UID: NF:winppi.GdiDeleteSpoolFileHandle
title: GdiDeleteSpoolFileHandle function
author: windows-driver-content
description: The GdiDeleteSpoolFileHandle function releases a spool file handle.
old-location: print\gdideletespoolfilehandle.htm
old-project: print
ms.assetid: ff22498e-404f-42f6-82fd-f0178f6c7789
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GdiDeleteSpoolFileHandle, GdiDeleteSpoolFileHandle function [Print Devices], gdifnc_76c1c0cf-2a48-44eb-9b48-1d0a5bf4548b.xml, print.gdideletespoolfilehandle, winppi/GdiDeleteSpoolFileHandle
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
req.lib: Gdi32.lib
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
-	GdiDeleteSpoolFileHandle
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# GdiDeleteSpoolFileHandle function


## -description


The <b>GdiDeleteSpoolFileHandle</b> function releases a spool file handle.


## -parameters




### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549517">GdiGetSpoolFileHandle</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.




## -remarks



The <b>GdiDeleteSpoolFileHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560724">PrintDocumentOnPrintProcessor</a> function.

Print processors should call <b>GdiDeleteSpoolFileHandle</b> after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549463">GdiEndDocEMF</a>, when processing a print job's EMF data stream has been completed. The function calls ClosePrinter (described in the Microsoft Window SDK documentation) to close the printer connection.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549517">GdiGetSpoolFileHandle</a>
 

 

