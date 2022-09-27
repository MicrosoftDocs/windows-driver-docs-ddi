---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_BidiNotification
title: IPrinterExtensionEventArgs::get_BidiNotification (printerextension.h)
description: Gets the text of the bidirectional communication (Bidi) notification, if applicable.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionEventArgs::get_BidiNotification"]
ms.keywords: BidiNotification property [Print Devices], BidiNotification property [Print Devices],IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs interface [Print Devices],BidiNotification property, IPrinterExtensionEventArgs.BidiNotification, IPrinterExtensionEventArgs.get_BidiNotification, IPrinterExtensionEventArgs::BidiNotification, IPrinterExtensionEventArgs::get_BidiNotification, get_BidiNotification, print.iprinterextensioneventargs_bidinotification, printerextension/IPrinterExtensionEventArgs::BidiNotification, printerextension/IPrinterExtensionEventArgs::get_BidiNotification
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
 - IPrinterExtensionEventArgs::get_BidiNotification
 - printerextension/IPrinterExtensionEventArgs::get_BidiNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_BidiNotification
---

## -description

Gets the text of the bidirectional communication (Bidi) notification, if applicable.

This property is read-only.

## -parameters

### -param pbstrBidiNotification

Defines the **BSTR** parameter *pbstrBidiNotification*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrinterExtensionEventArgs](./nn-printerextension-iprinterextensioneventargs.md)