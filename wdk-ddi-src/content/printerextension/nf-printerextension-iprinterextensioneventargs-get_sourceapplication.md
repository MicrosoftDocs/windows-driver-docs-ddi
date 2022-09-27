---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_SourceApplication
title: IPrinterExtensionEventArgs::get_SourceApplication (printerextension.h)
description: Gets the name of the application that invoked the printer extension.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrinterExtensionEventArgs::get_SourceApplication"]
ms.keywords: IPrinterExtensionEventArgs interface [Print Devices],SourceApplication property, IPrinterExtensionEventArgs.SourceApplication, IPrinterExtensionEventArgs.get_SourceApplication, IPrinterExtensionEventArgs::SourceApplication, IPrinterExtensionEventArgs::get_SourceApplication, SourceApplication property [Print Devices], SourceApplication property [Print Devices],IPrinterExtensionEventArgs interface, get_SourceApplication, print.iprinterextensioneventargs_sourceapplication, printerextension/IPrinterExtensionEventArgs::SourceApplication, printerextension/IPrinterExtensionEventArgs::get_SourceApplication
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrinterExtensionEventArgs::get_SourceApplication
 - printerextension/IPrinterExtensionEventArgs::get_SourceApplication
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_SourceApplication
---

## -description

Gets the name of the application that invoked the printer extension.

This property is read-only.

## -parameters

### -param pbstrApplication

Defines the **BSTR** parameter *pbstrApplication*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionEventArgs](./nn-printerextension-iprinterextensioneventargs.md)