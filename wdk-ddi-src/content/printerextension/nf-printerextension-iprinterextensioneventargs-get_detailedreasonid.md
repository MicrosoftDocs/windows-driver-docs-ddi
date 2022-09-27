---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_DetailedReasonId
title: IPrinterExtensionEventArgs::get_DetailedReasonId (printerextension.h)
description: Gets a more detailed activation reason than what can be retrieved from ReasonId.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrinterExtensionEventArgs::get_DetailedReasonId"]
ms.keywords: DetailedReasonId property [Print Devices], DetailedReasonId property [Print Devices],IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs interface [Print Devices],DetailedReasonId property, IPrinterExtensionEventArgs.DetailedReasonId, IPrinterExtensionEventArgs.get_DetailedReasonId, IPrinterExtensionEventArgs::DetailedReasonId, IPrinterExtensionEventArgs::get_DetailedReasonId, get_DetailedReasonId, print.iprinterextensioneventargs_detailedreasonid, printerextension/IPrinterExtensionEventArgs::DetailedReasonId, printerextension/IPrinterExtensionEventArgs::get_DetailedReasonId
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
 - IPrinterExtensionEventArgs::get_DetailedReasonId
 - printerextension/IPrinterExtensionEventArgs::get_DetailedReasonId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionEventArgs::get_DetailedReasonId
---

## -description

Gets a more detailed activation reason than what can be retrieved from [ReasonId](./nf-printerextension-iprinterextensioneventargs-get_reasonid.md).

This property is read-only.

## -parameters

### -param pDetailedReasonId

Defines the **GUID** parameter *pDetailedReasonId*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

The value of **DetailedReasonId** is always {5D5A1704-DFD1-4181-8EEE-815C86EDAD31}, which indicates that the printer extension was activated as  a result of a Bidi event.

## -see-also

[IPrinterExtensionEventArgs](./nn-printerextension-iprinterextensioneventargs.md)

[ReasonId](./nf-printerextension-iprinterextensioneventargs-get_reasonid.md)