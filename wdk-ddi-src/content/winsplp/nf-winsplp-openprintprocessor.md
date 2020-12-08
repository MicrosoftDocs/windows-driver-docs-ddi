---
UID: NF:winsplp.OpenPrintProcessor
title: OpenPrintProcessor function (winsplp.h)
description: A print processor's OpenPrintProcessor function prepares the print processor for printing a job and returns a handle.
old-location: print\openprintprocessor.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["OpenPrintProcessor function"]
ms.keywords: OpenPrintProcessor, OpenPrintProcessor function [Print Devices], print.openprintprocessor, spoolfnc_b8a185f0-4289-49bb-bb98-b6f54b66fa70.xml, winsplp/OpenPrintProcessor
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
req.lib: Nwprint.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - OpenPrintProcessor
 - winsplp/OpenPrintProcessor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Nwprint.lib
 - Nwprint.dll
api_name:
 - OpenPrintProcessor
---

# OpenPrintProcessor function


## -description

A print processor's <code>OpenPrintProcessor</code> function prepares the print processor for printing a job and returns a handle.

## -parameters

### -param pPrinterName 

[in]
Caller-supplied pointer to the name of the printer for which the print processor is being opened.

### -param pPrintProcessorOpenData 

[in]
Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure.

## -returns

If the operation succeeds, the function should return a handle that can be used as an input argument for subsequent calls to <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>, <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-controlprintprocessor">ControlPrintProcessor</a>, and <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-closeprintprocessor">ClosePrintProcessor</a>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>NULL</b>.

## -remarks

Print processors are required to export an <code>OpenPrintProcessor</code> function. The spooler calls the function when a print job is available. The function should perform initialization operations that are required before a job can be processed, based on the job's data type.

The function must return a handle. Typically, the handle is a pointer to an internal structure. The structure must contain a pointer to the printer's name and a pointer to the printer's <a href="/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure, both of which are received in the <a href="/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure. These two pointers are required by the print processor's <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function, and this latter function receives the handle as input when the spooler calls it.

## -see-also

<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-closeprintprocessor">ClosePrintProcessor</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-controlprintprocessor">ControlPrintProcessor</a>



<a href="/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_printprocessoropendata">PRINTPROCESSOROPENDATA</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>
