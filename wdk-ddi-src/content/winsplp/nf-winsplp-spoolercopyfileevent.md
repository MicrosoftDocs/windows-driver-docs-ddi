---
UID: NF:winsplp.SpoolerCopyFileEvent
title: SpoolerCopyFileEvent function (winsplp.h)
description: A Point and Print DLL's SpoolerCopyFileEvent function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server.
tech.root: print
ms.date: 03/09/2023
keywords: ["SpoolerCopyFileEvent function"]
ms.keywords: SpoolerCopyFileEvent, SpoolerCopyFileEvent function [Print Devices], poprfnc_e85f9707-18cf-4cd5-aece-ebcd5fd09270.xml, print.spoolercopyfileevent, winsplp/SpoolerCopyFileEvent
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Universal
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - SpoolerCopyFileEvent
 - winsplp/SpoolerCopyFileEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Mscms.dll
api_name:
 - SpoolerCopyFileEvent
---

## -description

A Point and Print DLL's **SpoolerCopyFileEvent** function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server.

## -parameters

### -param pszPrinterName [in]

Caller-supplied pointer to a string representing the printer name.

### -param pszKey [in]

Caller-supplied pointer to a string representing a subkey under the printer's **CopyFiles** registry key. This subkey identifies the component to which the Point and Print DLL belongs.

### -param dwCopyFileEvent [in]

Caller-supplied flag that identifies the event being reported. Valid flag values are contained in the following table.

| Flag | When Received | Where Received |
|---|---|---|
| COPYFILE_EVENT_ADD_PRINTER_CONNECTION | After a client application has called **AddPrinterConnection**. | Client copy of `SpoolerCopyFileEvent`. The calling context is the client application. |
| COPYFILE_EVENT_DELETE_PRINTER | After a call to **DeletePrinter** has been made. | Client copy of `SpoolerCopyFileEvent`. The calling context is the client's spooler. |
| COPYFILE_EVENT_DELETE_PRINTER_CONNECTION | After a client application has called **DeletePrinterConnection**. | Client copy of `SpoolerCopyFileEvent`. The calling context is the client application. |
| COPYFILE_EVENT_FILES_CHANGED | After the client has downloaded the files specified under the **pszKey** subkey of the printer's **CopyFiles** registry key. | Client copy of `SpoolerCopyFileEvent`. The calling context is the client's spooler. |
| COPYFILE_EVENT_SET_PRINTER_DATAEX | After a call to **SetPrinterDataEx** has been processed on the server. | Server copy of `SpoolerCopyFileEvent`. The calling context is the client application, by impersonation. |

## -returns

If the function encounters errors, the function should return **FALSE**. Otherwise, it should return **TRUE**.

## -remarks

All [Point and Print DLLs](/windows-hardware/drivers/print/point-and-print-dlls) must export a **SpoolerCopyFileEvent** function, which is called by the print spooler. Its purpose is to allow a Point and Print DLL to be notified of events related to the downloading of print queue-associated files, from a print server to a client system, when an application on the client connects to the server. For a complete description of the steps involved in creating a Point and Print connection, see [Supporting Point and Print](/windows-hardware/drivers/print/supporting-point-and-print).

A Point and Print DLL executes on both the server and the client. The **SpoolerCopyFileEvent** function can determine where it is executing by reading the contents of *dwCopyFileEvent*, which supplies a flag indicating the event. The function should process the event and return. If no processing is necessary, the function should just return **TRUE**.

If *dwCopyFileEvent* is COPYFILE_EVENT_ADD_PRINTER_CONNECTION or COPYFILE_EVENT_ADD_PRINTER_CONNECTION, the string supplied by *pszPrinterName* includes the server name.

## -see-also

[GenerateCopyFilePaths](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-generatecopyfilepaths)
