---
UID: NF:winsplp.InitializePrintProvidor
title: InitializePrintProvidor function (winsplp.h)
description: A print provider's InitializePrintProvidor function initializes the provider and supplies the print spooler with the provider's entry points.
tech.root: print
ms.date: 11/30/2022
keywords: ["InitializePrintProvidor function"]
ms.keywords: InitializePrintProvidor, InitializePrintProvidor function [Print Devices], print.initializeprintprovidor, spoolfnc_b67588a9-bccb-4181-8fd0-cbdc1b7af7c5.xml, winsplp/InitializePrintProvidor
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
 - InitializePrintProvidor
 - winsplp/InitializePrintProvidor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - InitializePrintProvidor
---

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

A print provider's **InitializePrintProvidor** function initializes the provider and supplies the print spooler with the provider's entry points.

## -parameters

### -param pPrintProvidor [out]

Caller-supplied address of a [**PRINTPROVIDOR**](./ns-winsplp-_printprovidor.md) structure, to be filled in by the print provider.

### -param cbPrintProvidor [in]

Caller-supplied size, in bytes, of the PRINTPROVIDOR structure pointed to by *pPrintProvidor*.

### -param pFullRegistryPath [in, optional]

Caller-supplied pointer to a string representing the full registry path to the provider's registry entry.

## -returns

If the operation succeeds, the function should return **TRUE**. Otherwise the function should return **FALSE**.

## -remarks

Print providers are required to define an **InitializePrintProvidor** function, which is the first function called by the spooler after the provider has been loaded. The function must fill the supplied [**PRINTPROVIDOR**](./ns-winsplp-_printprovidor.md) structure with pointers to the provider's defined functions (see [Functions defined by print providers](/windows-hardware/drivers/print/functions-defined-by-print-providers)). The function can also perform other provider-specific initialization operations.

## -see-also

[**PRINTPROVIDOR**](./ns-winsplp-_printprovidor.md)