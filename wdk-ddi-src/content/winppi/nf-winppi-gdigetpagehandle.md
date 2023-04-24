---
UID: NF:winppi.GdiGetPageHandle
title: GdiGetPageHandle function (winppi.h)
description: The GdiGetPageHandle function returns a handle to the specified page within a print job.
tech.root: print
ms.date: 03/09/2023
keywords: ["GdiGetPageHandle function"]
ms.keywords: GdiGetPageHandle, GdiGetPageHandle function [Print Devices], gdifnc_3a8cdbd2-c73f-4b24-b984-9237b20327e1.xml, print.gdigetpagehandle, winppi/GdiGetPageHandle
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
 - GdiGetPageHandle
 - winppi/GdiGetPageHandle
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
 - GdiGetPageHandle
---

## -description

The **GdiGetPageHandle** function returns a handle to the specified page within a print job.

## -parameters

### -param SpoolFileHandle

Caller-supplied spool file handle, obtained by a previous call to [GdiGetSpoolFileHandle](./nf-winppi-gdigetspoolfilehandle.md).

### -param Page

Caller-supplied page number.

### -param pdwPageType

Caller-supplied pointer to a location that receives the page type. The possible page types are shown in the following table:

| Page Type | Meaning |
|---|---|
| EMF_PP_FORM | The page is a form or has a watermark. (Not currently supported.) |
| EMF_PP_NORMAL | The page is a normal page. |

## -returns

If the operation succeeds, the function returns **TRUE**. Otherwise the function returns **FALSE**, and an error code can be obtained by calling **GetLastError**.

## -remarks

The **GdiGetPageHandle** function is exported by gdi32.dll for use within a print processor's [PrintDocumentOnPrintProcessor](../winsplp/nf-winsplp-printdocumentonprintprocessor.md) function.

Print processors must obtain a page handle before calling [GdiPlayPageEMF](./nf-winppi-gdiplaypageemf.md) to draw a page. If a Page value is specified that is too large, the function returns ERROR_NO_MORE_ITEMS.

For additional information, see [Using GDI Functions in Print Processors](/windows-hardware/drivers/print/using-gdi-functions-in-print-processors).