---
UID: NF:printerextension.IPrintJob.get_Status
title: IPrintJob::get_Status method (printerextension.h)
description: Gets the current status of the print job.
tech.root: print
ms.date: 07/29/2022
keywords: ["IPrintJob::get_Status method"]
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], Status property, IPrintJob.Status, IPrintJob::get_Status, Status property [Print Devices], Status property [Print Devices], IPrintJob interface, get_Status, get_Status,IPrintJob.get_Status, print.iprintjob_status, printerextension/IPrintJob::Status, printerextension/IPrintJob::get_Status
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
f1_keywords:
 - IPrintJob::get_Status
 - printerextension/IPrintJob::get_Status
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJob::get_Status
---

## -description

Gets the current status of the print job.

This property is read-only.

## -parameters

### -param pStatus

Defines the **PrintJobStatus** parameter *pStatus*.

## -returns

Returns an **HRESULT** value.

## -see-also

[IPrintJob](./nn-printerextension-iprintjob.md)

[PrintJobStatus](./ne-printerextension-tagprintjobstatus.md)