---
UID: NF:printerextension.IPrinterExtensionManager.EnableEvents
title: IPrinterExtensionManager::EnableEvents (printerextension.h)
description: The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterExtensionManager::EnableEvents"]
ms.keywords: EnableEvents, EnableEvents method [Print Devices], EnableEvents method [Print Devices],IPrinterExtensionManager interface, IPrinterExtensionManager interface [Print Devices],EnableEvents method, IPrinterExtensionManager.EnableEvents, IPrinterExtensionManager::EnableEvents, print.iprinterextensionmanager_enableevents, printerextension/IPrinterExtensionManager::EnableEvents
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
 - IPrinterExtensionManager::EnableEvents
 - printerextension/IPrinterExtensionManager::EnableEvents
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterExtensionManager::EnableEvents
---

## -description

The EnableEvents method allows events to be generated for the specified printer driver until  [DisableEvents](./nf-printerextension-iprinterextensionmanager-disableevents.md) is called.

## -parameters

### -param printerDriverId [in]

The GUID representing the specified driver for which to enable events. This GUID is specified in the INF file, and is also specified by the manifest file directive 'PrinterDriverID'.

## -returns

This method returns an **HRESULT** value.

The printer extension should call this method when it is launched so that driver events are generated for it to consume.

## -remarks

In the case of a driver event like, for example, Print Preferences or Printer Notifications, the app is expected to call **EnableEvents**. But if the app doesn't call **EnableEvents** within 5 seconds, the print system assumes that a UI was  called but it's not being responsive so a standard UI is displayed instead.

## -see-also

[IPrinterExtensionManager](./nn-printerextension-iprinterextensionmanager.md)