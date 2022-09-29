---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_WindowParent
title: IPrinterExtensionEventArgs::get_WindowParent (printerextension.h)
description: Gets the handle of the parent window.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionEventArgs::get_WindowParent"]
ms.keywords: IPrinterExtensionEventArgs interface [Print Devices],WindowParent property, IPrinterExtensionEventArgs.WindowParent, IPrinterExtensionEventArgs.get_WindowParent, IPrinterExtensionEventArgs::WindowParent, IPrinterExtensionEventArgs::get_WindowParent, WindowParent property [Print Devices], WindowParent property [Print Devices],IPrinterExtensionEventArgs interface, get_WindowParent, print.iprinterextensioneventargs_windowparent, printerextension/IPrinterExtensionEventArgs::WindowParent, printerextension/IPrinterExtensionEventArgs::get_WindowParent
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
 - IPrinterExtensionEventArgs::get_WindowParent
 - printerextension/IPrinterExtensionEventArgs::get_WindowParent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_WindowParent
---

## -description

Gets the handle of the parent window.

This property is read-only.

## -parameters

### -param phwndParent

Defines the **HANDLE** parameter *phwndParent*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionEventArgs](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioneventargs)
