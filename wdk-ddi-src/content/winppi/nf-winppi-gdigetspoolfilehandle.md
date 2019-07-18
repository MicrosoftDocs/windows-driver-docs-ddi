---
UID: NF:winppi.GdiGetSpoolFileHandle
title: GdiGetSpoolFileHandle function (winppi.h)
description: The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file.
old-location: print\gdigetspoolfilehandle.htm
tech.root: print
ms.assetid: c820ee94-29c2-4478-884c-49dd68cd713a
ms.date: 04/20/2018
ms.keywords: GdiGetSpoolFileHandle, GdiGetSpoolFileHandle function [Print Devices], gdifnc_f7231fd8-33b0-4047-90ba-e5e2c9c37814.xml, print.gdigetspoolfilehandle, winppi/GdiGetSpoolFileHandle
ms.topic: function
f1_keywords:
 - "winppi/GdiGetSpoolFileHandle"
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
- GdiGetSpoolFileHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# GdiGetSpoolFileHandle function


## -description


The <b>GdiGetSpoolFileHandle</b> function returns a handle to a print job's EMF file.


## -parameters




### -param pwszPrinterName

Caller-supplied pointer to a string representing the name of the target printer. See the following Remarks section.


### -param pDevmode

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure. See the following Remarks section.


### -param pwszDocName

Caller-supplied pointer to the print job's document name. See the following Remarks section.


## -returns



If the operation succeeds, the function returns a spool file handle. Otherwise the function returns <b>NULL</b>.




## -remarks



The <b>GdiGetSpoolFileHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

When a print processor calls <b>GdiGetSpoolFileHandle</b>, it should supply arguments as illustrated in the following table.

<table>
<tr>
<th>Parameter</th>
<th>Argument</th>
</tr>
<tr>
<td>
<i>pwszPrinterName</i>

</td>
<td>
Pointer to the printer name received by the print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a> function.

</td>
</tr>
<tr>
<td>
<i>pDevmode</i>

</td>
<td>
Pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/ns-winsplp-_printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure, received by the print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a> function.

</td>
</tr>
<tr>
<td>
<i>pwszDocName</i>

</td>
<td>
Document name pointer received by the print processor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

</td>
</tr>
</table>
 

A print processor must call the <b>GdiGetSpoolFileHandle</b> function before calling any other GDI printing functions, because the returned handle must be passed to the other functions. The function calls OpenPrinter to open a connection to the printer, and CreateDC to create a device context for drawing. The print processor can obtain the device context's handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdigetdc">GdiGetDC</a>.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-gdi-functions-in-print-processors">Using GDI Functions in Print Processors</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winppi/nf-winppi-gdideletespoolfilehandle">GdiDeleteSpoolFileHandle</a>
 

 

