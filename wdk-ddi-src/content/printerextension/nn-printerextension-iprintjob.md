---
UID: NN:printerextension.IPrintJob
title: IPrintJob (printerextension.h)
description: Contains properties that represent a print job.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrintJob interface"]
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], IPrintJob interface [Print Devices],described, print.iprintjob, printerextension/IPrintJob
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
req.typenames: 
f1_keywords:
 - IPrintJob
 - printerextension/IPrintJob
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJob
---

## -description

Contains properties that represent a print job.

This interface also provides a method that allows a print job to be cancelled.

## -inheritance

The **IPrintJob** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

The **IPrintJob** interface provides a wrapper around select properties of the spooler's [JOB_INFO_1](/windows/win32/printdocs/job-info-1) structure.

**IPrintJob** also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see [Job Management](/windows-hardware/drivers/print/job-management).

## -see-also

[JOB_INFO_1](/windows/win32/printdocs/job-info-1)

[Job Management](/windows-hardware/drivers/print/job-management)
