---
UID: NN:printerextension.IPrinterQueue2
title: IPrinterQueue2 (printerextension.h)
description: Learn how IPrinterQueue2 represents a single printer queue.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrinterQueue2 interface"]
ms.keywords: IPrinterQueue2, IPrinterQueue2 interface [Print Devices], IPrinterQueue2 interface [Print Devices],described, print.iprinterqueue2, printerextension/IPrinterQueue2
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrinterQueue2
 - printerextension/IPrinterQueue2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterQueue2
---

# IPrinterQueue2 interface

## -description

Represents a single printer queue.

This interface extends [IPrinterQueue](./nn-printerextension-iprinterqueue.md) and allows a user to manage print jobs and device maintenance from within a UWP  device app for printers, or from a printer extension.

## -inheritance

The **IPrinterQueue2** interface inherits from [IPrinterQueue](./nn-printerextension-iprinterqueue.md).

## -remarks

**IPrinterQueue2** also helps to make it possible to perform device maintenance and job management from a UWP  device app or from a printer extension. For more information, see [Device Maintenance](/windows-hardware/drivers/print/device-maintenance) and [Job Management](/windows-hardware/drivers/print/job-management).

## -see-also

[Device Maintenance](/windows-hardware/drivers/print/device-maintenance)

[IPrinterQueue](./nn-printerextension-iprinterqueue.md)

[Job Management](/windows-hardware/drivers/print/job-management)