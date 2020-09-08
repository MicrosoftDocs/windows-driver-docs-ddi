---
UID: NF:winspool.DeleteJobNamedProperty
title: DeleteJobNamedProperty function (winspool.h)
description: Deletes the named property for the specified print job on the specified printer.
old-location: print\deletejobnamedproperty.htm
tech.root: print
ms.assetid: 14F8C0A2-0D19-446E-8C2B-530A3AEDA879
ms.date: 04/20/2018
keywords: ["DeleteJobNamedProperty function"]
ms.keywords: DeleteJobNamedProperty, DeleteJobNamedProperty function [Print Devices], print.deletejobnamedproperty, winspool/DeleteJobNamedProperty
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
 - DeleteJobNamedProperty
 - winspool/DeleteJobNamedProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - spoolss.dll
 - WinSpool.drv
api_name:
 - DeleteJobNamedProperty
---

# DeleteJobNamedProperty function


## -description

Deletes the named property for the specified print job on the specified printer.

## -parameters

### -param hPrinter 

[in]
A handle to the printer object of interest. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/openprinter">OpenPrinter</a>, <a href="https://docs.microsoft.com/windows/win32/printdocs/openprinter2">OpenPrinter2</a>, or the <a href="https://docs.microsoft.com/windows/win32/printdocs/addprinter">AddPrinter</a> function to retrieve a printer handle.

### -param JobId 

[in]
Identifier that specifies the print job. You obtain a print job identifier by calling the <a href="https://docs.microsoft.com/windows/win32/printdocs/addjob">AddJob</a> function or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nf-printoem-oemstartdoc">StartDoc</a> function.

### -param pszName 

[in]
Name of the property that will be deleted.

## -returns

If the operation succeeds, the function returns <b>ERROR_SUCCESS.</b>

