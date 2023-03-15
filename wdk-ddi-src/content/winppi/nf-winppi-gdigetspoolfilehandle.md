---
UID: NF:winppi.GdiGetSpoolFileHandle
title: GdiGetSpoolFileHandle function (winppi.h)
description: The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file.
tech.root: print
ms.date: 03/09/2023
keywords: ["GdiGetSpoolFileHandle function"]
ms.keywords: GdiGetSpoolFileHandle, GdiGetSpoolFileHandle function [Print Devices], gdifnc_f7231fd8-33b0-4047-90ba-e5e2c9c37814.xml, print.gdigetspoolfilehandle, winppi/GdiGetSpoolFileHandle
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GdiGetSpoolFileHandle
 - winppi/GdiGetSpoolFileHandle
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
---

## -description

The **GdiGetSpoolFileHandle** function returns a handle to a print job's EMF file.

## -parameters

### -param pwszPrinterName

Caller-supplied pointer to a string representing the name of the target printer. See the following Remarks section.

### -param pDevmode

Caller-supplied pointer to a [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. See the following Remarks section.

### -param pwszDocName

Caller-supplied pointer to the print job's document name. See the following Remarks section.

## -returns

If the operation succeeds, the function returns a spool file handle. Otherwise the function returns **NULL**.

## -remarks

The **GdiGetSpoolFileHandle** function is exported by gdi32.dll for use within a print processor's [PrintDocumentOnPrintProcessor](../winsplp/nf-winsplp-printdocumentonprintprocessor.md) function.

When a print processor calls **GdiGetSpoolFileHandle**, it should supply arguments as illustrated in the following table.

| Parameter | Argument |
|---|---|
| *pwszPrinterName* | Pointer to the printer name received by the print processor's [OpenPrintProcessor](../winsplp/nf-winsplp-openprintprocessor.md) function. |
| *pDevmode* | Pointer to the [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure contained in the [**PRINTPROCESSOROPENDATA**](../winsplp/ns-winsplp-_printprocessoropendata.md) structure, received by the print processor's [OpenPrintProcessor](../winsplp/nf-winsplp-openprintprocessor.md) function. |
| *pwszDocName* | Document name pointer received by the print processor's [PrintDocumentOnPrintProcessor](../winsplp/nf-winsplp-printdocumentonprintprocessor.md) function. |

A print processor must call the **GdiGetSpoolFileHandle** function before calling any other GDI printing functions, because the returned handle must be passed to the other functions. The function calls OpenPrinter to open a connection to the printer, and CreateDC to create a device context for drawing. The print processor can obtain the device context's handle by calling [GdiGetDC](./nf-winppi-gdigetdc.md).

For additional information, see [Using GDI Functions in Print Processors](/windows-hardware/drivers/print/using-gdi-functions-in-print-processors).

## -see-also

[GdiDeleteSpoolFileHandle](./nf-winppi-gdideletespoolfilehandle.md)