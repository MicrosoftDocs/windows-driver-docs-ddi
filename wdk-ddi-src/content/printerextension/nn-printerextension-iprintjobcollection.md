---
UID: NN:printerextension.IPrintJobCollection
title: IPrintJobCollection (printerextension.h)
description: This interfaces provides an enumeration of the jobs in the print queue.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintJobCollection interface"]
ms.keywords: IPrintJobCollection, IPrintJobCollection interface [Print Devices], IPrintJobCollection interface [Print Devices],described, print.iprintjobcollection, printerextension/IPrintJobCollection
req.header: printerextension.h
req.include-header: 
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
 - IPrintJobCollection
 - printerextension/IPrintJobCollection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintJobCollection
---

# IPrintJobCollection interface

## -description

This interfaces provides an enumeration of the jobs in the print queue.

The enumerated list of jobs represents a snapshot of the current job status.

## -inheritance

The **IPrintJobCollection** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface. **IPrintJobCollection** also has these types of members:

## -remarks

The order of print jobs in the enumerated list is the same as the order provided by [EnumJobs](/windows/win32/printdocs/enumjobs), which is the actual print queue order.

**IPrintJobCollection** also helps to make it possible to perform job management from a UWP device app or from a printer extension. For more information, see [Job Management](/windows-hardware/drivers/print/job-management).

## -see-also

[EnumJobs](/windows/win32/printdocs/enumjobs)

[Job Management](/windows-hardware/drivers/print/job-management)
