---
UID: NF:winsplp.AddPrintDeviceObject
title: AddPrintDeviceObject function (winsplp.h)
description: The AddPrintDeviceObject print provider function creates a device object for a print provider queue.
tech.root: print
ms.date: 01/04/2023
keywords: ["AddPrintDeviceObject function"]
ms.keywords: AddPrintDeviceObject, AddPrintDeviceObject function [Print Devices], print.addprintdeviceobject, winsplp/AddPrintDeviceObject
req.header: winsplp.h
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
req.dll: WinSpool.drv
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AddPrintDeviceObject
 - winsplp/AddPrintDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - AddPrintDeviceObject
---

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

The **AddPrintDeviceObject** print provider function creates a device object for a print provider queue.

## -parameters

### -param hPrinter [in]

A HANDLE to an open printer. This should be a HANDLE returned by the **AddPrinter** or **OpenPrinter** spooler functions.

### -param phDeviceObject [out]

A HANDLE to the device object, if it was created successfully.

## -returns

The **AddPrintDeviceObject** function returns S_OK, if the device object was created successfully. Otherwise, it returns an error.

## -remarks

The **AddPrintDeviceObject** function should be called in the following situations:

### User installs a printer

- The print provider should call this function after installing the printer.

- The function must be called by impersonating the user who is installing the printer.

### Print provider is initialized after spooler service starts

The print provider should call this function for each previously-installed Printer owned by the provider. During this time, **AddPrintDeviceObject** doesn't have to impersonate the user context when it is called.

Any device object that is added using  **AddPrintDeviceObject** will persist until you remove it using [RemovePrintDeviceObject](./nf-winsplp-removeprintdeviceobject.md), or until the spooler service restarts. And when the spooler services stops, all the device objects are automatically deleted.

## -see-also

[RemovePrintDeviceObject](./nf-winsplp-removeprintdeviceobject.md)