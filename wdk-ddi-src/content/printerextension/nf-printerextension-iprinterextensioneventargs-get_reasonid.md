---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_ReasonId
title: IPrinterExtensionEventArgs::get_ReasonId (printerextension.h)
description: Gets the reason why the printer extension was activated.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrinterExtensionEventArgs::get_ReasonId"]
ms.keywords: IPrinterExtensionEventArgs interface [Print Devices],ReasonId property, IPrinterExtensionEventArgs.ReasonId, IPrinterExtensionEventArgs.get_ReasonId, IPrinterExtensionEventArgs::ReasonId, IPrinterExtensionEventArgs::get_ReasonId, ReasonId property [Print Devices], ReasonId property [Print Devices],IPrinterExtensionEventArgs interface, get_ReasonId, print.iprinterextensioneventargs_reasonid, printerextension/IPrinterExtensionEventArgs::ReasonId, printerextension/IPrinterExtensionEventArgs::get_ReasonId
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
 - IPrinterExtensionEventArgs::get_ReasonId
 - printerextension/IPrinterExtensionEventArgs::get_ReasonId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_ReasonId
---

## -description

Gets the reason why the printer extension was activated.

This property is read-only.

## -parameters

### -param pReasonId

Defines the **GUID** parameter *pReasonId*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

In this mode, preferences for a print job or default print preferences is expected to be displayed:

- Guid = {EC8F261F-267C-469F-B5D6-3933023C29CC}

- **PRINTER_EXTENSION_REASON_PRINT_PREFERENCES** = { 0xec8f261f, 0x267c, 0x469f, 0xb5, 0xd6, 0x39, 0x33, 0x2, 0x3c, 0x29, 0xcc };

In this mode a status monitor for the print queue is expected to be displayed:

- Guid = {23BB1328-63DE-4293-915B-A6A23D929ACB}

- **PRINTER_EXTENSION_REASON_DRIVER_EVENT** = { 0x23bb1328, 0x63de, 0x4293, 0x91, 0x5b, 0xa6, 0xa2, 0x3d, 0x92, 0x9a, 0xcb };

## -see-also

[DetailedReasonId](./nf-printerextension-iprinterextensioneventargs-get_detailedreasonid.md)

[IPrinterExtensionEventArgs](./nn-printerextension-iprinterextensioneventargs.md)