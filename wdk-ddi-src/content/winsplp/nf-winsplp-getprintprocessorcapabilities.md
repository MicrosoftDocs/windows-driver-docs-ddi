---
UID: NF:winsplp.GetPrintProcessorCapabilities
title: GetPrintProcessorCapabilities function (winsplp.h)
description: A print processor's GetPrintProcessorCapabilities function returns capabilities associated with a specified input data type.
tech.root: print
ms.date: 11/30/2022
keywords: ["GetPrintProcessorCapabilities function"]
ms.keywords: GetPrintProcessorCapabilities, GetPrintProcessorCapabilities function [Print Devices], print.getprintprocessorcapabilities, spoolfnc_4ca0ae34-060f-4144-91de-a2556d1b5261.xml, winsplp/GetPrintProcessorCapabilities
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - GetPrintProcessorCapabilities
 - winsplp/GetPrintProcessorCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - GetPrintProcessorCapabilities
---

## -description

A print processor's **GetPrintProcessorCapabilities** function returns capabilities associated with a specified input data type.

## -parameters

### -param pValueName [in]

Caller-supplied pointer to a string that represents a data type that is supported by the print processor. The string pointer must be of type LPWSTR.

### -param dwAttributes [in]

Caller-supplied attributes flags. Refer to the **Attributes** member of **PRINTER_INFO_*x*** structures.

### -param pData [out]

Caller-supplied pointer to a [**PRINTPROCESSOR_CAPS_1**](/windows/win32/printdocs/printprocessor-caps-1) or [**PRINTPROCESSOR_CAPS_2**](/windows/win32/printdocs/printprocessor-caps-2) structure.

### -param nSize [in]

Caller-supplied value that represents the size of the buffer pointed to by *pData*.

If the value is less than sizeof(PRINTPROCESSOR_CAPS_1), this function should supply a value that is equal to sizeof(PRINTPROCESSOR_CAPS_1) or sizeof(PRINTPROCESSOR_CAPS_2), depending on which structure is supported by the print processor.

> [!NOTE]
> If the value is less than sizeof(PRINTPROCESSOR_CAPS_1), the winprint print processor will supply a value of sizeof(PRINTPROCESSOR_CAPS_2).

### -param pcbNeeded [out]

Caller-supplied pointer to a location to receive the minimum required size for the buffer pointed to by *pData*.

## -returns

If the operation succeeds, the function should return ERROR_SUCCESS. Otherwise, it should return a Win32 error code.

## -remarks

Print processors can optionally export a **GetPrintProcessorCapabilities** function. The function's purpose is to return a filled-in PRINTPROCESSOR_CAPS_1 or PRINTPROCESSOR_CAPS_2 structure for every input data type that the print processor supports.

The spooler calls a print processor's **GetPrintProcessorCapabilities** function when an application calls [**GetPrinterData**](/windows/win32/printdocs/getprinterdata), specifying a value name with a format of PrintProcCaps_*datatype*, where *datatype* is the name of an input data type. Before calling **GetPrintProcessorCapabilities,** the spooler removes the PrintProcCaps_ prefix from the value name string.

The function should determine if the received buffer is large enough and, if it is, should fill in either the [**PRINTPROCESSOR_CAPS_1**](/windows/win32/printdocs/printprocessor-caps-1) or [**PRINTPROCESSOR_CAPS_2**](/windows/win32/printdocs/printprocessor-caps-2) structure and return. The value of *nSize* determines whether **PRINTPROCESSOR_CAPS_1** or **PRINTPROCESSOR_CAPS_2** will be used.

The function should always use the location pointed to by *pcbNeeded* to return the required buffer size, whether or not the actual buffer is large enough.

The specified return value becomes the return value that the spooler provides for **GetPrinterData**.
