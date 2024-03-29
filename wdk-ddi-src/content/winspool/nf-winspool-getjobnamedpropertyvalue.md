---
UID: NF:winspool.GetJobNamedPropertyValue
title: GetJobNamedPropertyValue function (winspool.h)
description: Retrieves the value of the named property for the specified print job on the specified printer.
old-location: print\getjobnamedpropertyvalue.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["GetJobNamedPropertyValue function"]
ms.keywords: GetJobNamedPropertyValue, GetJobNamedPropertyValue function [Print Devices], print.getjobnamedpropertyvalue, winspool/GetJobNamedPropertyValue
req.header: winspool.h
req.include-header: Winspool.h
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
req.lib: WinSpool.lib
req.dll: Spoolss.dll; WinSpool.drv
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - GetJobNamedPropertyValue
 - winspool/GetJobNamedPropertyValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - spoolss.dll
 - WinSpool.drv
api_name:
 - GetJobNamedPropertyValue
---

# GetJobNamedPropertyValue function


## -description

Retrieves the value of the named property for the specified print job on the specified printer.

## -parameters

### -param hPrinter [in]


A handle to the printer object of interest. Use the <a href="/windows-hardware/drivers/print/openprinter">OpenPrinter</a>, <a href="/windows/win32/printdocs/openprinter2">OpenPrinter2</a>, or the <a href="/windows/win32/printdocs/addprinter">AddPrinter</a> function to retrieve a printer handle.

### -param JobId [in]


Identifier that specifies the print job. You obtain a print job identifier by calling the <a href="/windows/win32/printdocs/addjob">AddJob</a> function or the <a href="/windows-hardware/drivers/ddi/printoem/nf-printoem-oemstartdoc">StartDoc</a> function.

### -param pszName [in]


Name of the property whose value will be retrieved.

### -param pValue [out]


Value of the named property. The caller needs to free this using the <a href="/windows-hardware/drivers/ddi/winspool/nf-winspool-freeprintpropertyvalue">FreePrintPropertyValue</a> function.

## -returns

If the operation succeeds, the function returns <b>ERROR_SUCCESS</b>.
