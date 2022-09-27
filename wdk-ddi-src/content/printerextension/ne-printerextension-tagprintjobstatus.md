---
UID: NE:printerextension.tagPrintJobStatus
title: PrintJobStatus (printerextension.h)
description: This enumeration is a one-to-one mapping to the spooler flags supplied in the JOB_INFO_X structures.
tech.root: print
ms.date: 08/01/2022
keywords: ["tagPrintJobStatus enumeration"]
ms.keywords: PrintJobStatus, PrintJobStatus enumeration [Print Devices], PrintJobStatus_BlockedDeviceQueue, PrintJobStatus_Complete, PrintJobStatus_Deleted, PrintJobStatus_Deleting, PrintJobStatus_Error, PrintJobStatus_Offline, PrintJobStatus_PaperOut, PrintJobStatus_Paused, PrintJobStatus_Printed, PrintJobStatus_Printing, PrintJobStatus_Restarted, PrintJobStatus_Retained, PrintJobStatus_Spooling, PrintJobStatus_UserIntervention, print.printjobstatus, printerextension/PrintJobStatus, printerextension/PrintJobStatus_BlockedDeviceQueue, printerextension/PrintJobStatus_Complete, printerextension/PrintJobStatus_Deleted, printerextension/PrintJobStatus_Deleting, printerextension/PrintJobStatus_Error, printerextension/PrintJobStatus_Offline, printerextension/PrintJobStatus_PaperOut, printerextension/PrintJobStatus_Paused, printerextension/PrintJobStatus_Printed, printerextension/PrintJobStatus_Printing, printerextension/PrintJobStatus_Restarted, printerextension/PrintJobStatus_Retained, printerextension/PrintJobStatus_Spooling, printerextension/PrintJobStatus_UserIntervention, tagPrintJobStatus
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
req.typenames: PrintJobStatus
f1_keywords:
 - tagPrintJobStatus
 - printerextension/tagPrintJobStatus
 - PrintJobStatus
 - printerextension/PrintJobStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Printerextension.h
api_name:
 - tagPrintJobStatus
 - PrintJobStatus
---

## -description

This enumeration is a one-to-one mapping to the spooler flags supplied in the JOB_INFO_X structures.

For example, [JOB_INFO_1](/windows/win32/printdocs/job-info-1) has the same set of status flags as shown in the following list.

## -enum-fields

### -field PrintJobStatus_Paused

The job is paused.

### -field PrintJobStatus_Error

There is an error associated with the job.

### -field PrintJobStatus_Deleting

The job is being deleted.

### -field PrintJobStatus_Spooling

The job is spooling.

### -field PrintJobStatus_Printing

The job is printing.

### -field PrintJobStatus_Offline

The printer is offline.

### -field PrintJobStatus_PaperOut

The printer is out of paper.

### -field PrintJobStatus_Printed

The job printing is completed.

### -field PrintJobStatus_Deleted

The job has been deleted.

### -field PrintJobStatus_BlockedDeviceQueue

The driver cannot print the job.

### -field PrintJobStatus_UserIntervention

The printer has an error that requires intervention from the user.

### -field PrintJobStatus_Restarted

The job has been restarted.

### -field PrintJobStatus_Complete

The job data transfer to the printer is complete. Note that  the printing of the job may not yet be complete.

### -field PrintJobStatus_Retained

The job has been retained in the print queue and cannot be deleted.

## -remarks

A **PrintJobStatus_Retained** flag can be raised for several reasons. For example, jobs could be kept in the queue if the administrator of the queue used the desktop print queue UI to set the "Keep Printed Jobs" feature to be on.

It is possible for a job to have multiple  flag values specified simultaneously.

## -see-also

[IPrintJob::Status](./nf-printerextension-iprintjob-get_status.md)

[JOB_INFO_1](/windows/win32/printdocs/job-info-1)