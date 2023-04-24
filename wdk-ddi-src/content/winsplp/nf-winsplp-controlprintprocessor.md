---
UID: NF:winsplp.ControlPrintProcessor
title: ControlPrintProcessor function (winsplp.h)
description: A print processor's ControlPrintProcessor function allows the spooler to control a print job.
tech.root: print
ms.date: 03/09/2023
keywords: ["ControlPrintProcessor function"]
ms.keywords: ControlPrintProcessor, ControlPrintProcessor function [Print Devices], print.controlprintprocessor, spoolfnc_203120f1-7819-448e-9813-3aa2b24bfd7f.xml, winsplp/ControlPrintProcessor
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Nwprint.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ControlPrintProcessor
 - winsplp/ControlPrintProcessor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Nwprint.lib
 - Nwprint.dll
api_name:
 - ControlPrintProcessor
---

## -description

A print processor's **ControlPrintProcessor** function allows the spooler to control a print job.

## -parameters

### -param hPrintProcessor [in]

Caller-supplied print processor handle. This is the handle returned by a previous call to [OpenPrintProcessor](./nf-winsplp-openprintprocessor.md).

### -param Command [in]

Caller-supplied command indicating the type of operation to perform. The following commands are valid:

| Command | Definition |
|---|---|
| JOB_CONTROL_CANCEL | The function should cancel the current print job. |
| JOB_CONTROL_PAUSE | The function should pause the current print job. |
| JOB_CONTROL_RESUME | The function should resume the current print job. |

## -returns

If the operation succeeds, the function should return **TRUE**. If the operation fails, the function should call SetLastError to set an error code, and then return **FALSE**.

## -remarks

Print processors are required to export a **ControlPrintProcessor** function. The spooler calls the function when an application calls the SetJob function, described in the Microsoft Windows SDK documentation.

Based on the value received for *Command*, the function should either pause, resume, or cancel the current job. The **ControlPrintProcessor** function can be called asynchronously while the print processor's [PrintDocumentOnPrintProcessor](./nf-winsplp-printdocumentonprintprocessor.md) function is executing. Thus some sort of synchronization technique must be employed, such as setting an internally-defined event object to pause a job and resetting the event object when the job is resumed. The **ControlPrintProcessor** function can quickly return after setting or resetting the event object, and PrintDocumentOnPrintProcessor can wait for the event to be in the proper state.

## -see-also

[OpenPrintProcessor](./nf-winsplp-openprintprocessor.md)

[PrintDocumentOnPrintProcessor](./nf-winsplp-printdocumentonprintprocessor.md)