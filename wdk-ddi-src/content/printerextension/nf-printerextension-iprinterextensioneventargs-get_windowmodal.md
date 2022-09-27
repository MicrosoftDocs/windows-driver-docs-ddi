---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_WindowModal
title: IPrinterExtensionEventArgs::get_WindowModal (printerextension.h)
description: Gets the run mode parameter that determines whether or not the printer extension should be run as modal.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionEventArgs::get_WindowModal"]
ms.keywords: IPrinterExtensionEventArgs interface [Print Devices],WindowModal property, IPrinterExtensionEventArgs.WindowModal, IPrinterExtensionEventArgs.get_WindowModal, IPrinterExtensionEventArgs::WindowModal, IPrinterExtensionEventArgs::get_WindowModal, WindowModal property [Print Devices], WindowModal property [Print Devices],IPrinterExtensionEventArgs interface, get_WindowModal, print.iprinterextensioneventargs_windowmodal, printerextension/IPrinterExtensionEventArgs::WindowModal, printerextension/IPrinterExtensionEventArgs::get_WindowModal
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
 - IPrinterExtensionEventArgs::get_WindowModal
 - printerextension/IPrinterExtensionEventArgs::get_WindowModal
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_WindowModal
---

## -description

Gets the run mode parameter that determines whether or not the printer extension should be run as modal.

This property is read-only.

## -parameters

### -param pbModal

Defines the **BOOL** parameter *pbModal*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionEventArgs](./nn-printerextension-iprinterextensioneventargs.md)