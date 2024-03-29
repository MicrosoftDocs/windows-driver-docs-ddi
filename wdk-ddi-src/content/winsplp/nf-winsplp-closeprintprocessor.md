---
UID: NF:winsplp.ClosePrintProcessor
title: ClosePrintProcessor function (winsplp.h)
description: A print processor's ClosePrintProcessor function completes the printing of a print job and makes the associated handle invalid.
old-location: print\closeprintprocessor.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["ClosePrintProcessor function"]
ms.keywords: ClosePrintProcessor, ClosePrintProcessor function [Print Devices], print.closeprintprocessor, spoolfnc_f2e791a0-bfae-463c-a7ac-0e9f941ebe51.xml, winsplp/ClosePrintProcessor
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
 - ClosePrintProcessor
 - winsplp/ClosePrintProcessor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Nwprint.lib
 - Nwprint.dll
api_name:
 - ClosePrintProcessor
---

# ClosePrintProcessor function


## -description

A print processor's <b>ClosePrintProcessor</b> function completes the printing of a print job and makes the associated handle invalid.

## -parameters

### -param hPrintProcessor [in, out]


Caller-supplied print processor handle. This is the handle returned by a previous call to <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a>.

## -returns

If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call SetLastError to set an error code, and then return <b>FALSE</b>.

## -remarks

Print processors are required to export a <b>ClosePrintProcessor</b> function. The spooler calls the function after the print processor's <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> returns. The function should free all resources that were allocated by the <a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-openprintprocessor">OpenPrintProcessor</a>



<a href="/windows-hardware/drivers/ddi/winsplp/nf-winsplp-printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>
