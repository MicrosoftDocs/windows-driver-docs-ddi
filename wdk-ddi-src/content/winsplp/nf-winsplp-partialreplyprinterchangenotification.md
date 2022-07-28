---
UID: NF:winsplp.PartialReplyPrinterChangeNotification
title: PartialReplyPrinterChangeNotification function (winsplp.h)
description: The print spooler's PartialReplyPrinterChangeNotification function allows a print provider to update the spooler's database of printer changes associated with a notification handle.
tech.root: print
ms.date: 07/27/2022
keywords: ["PartialReplyPrinterChangeNotification function"]
ms.keywords: PartialReplyPrinterChangeNotification, PartialReplyPrinterChangeNotification function [Print Devices], print.partialreplyprinterchangenotification, spoolfnc_95f9f0ac-2340-463b-9c8d-6c27130020d9.xml, winsplp/PartialReplyPrinterChangeNotification
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PartialReplyPrinterChangeNotification
 - winsplp/PartialReplyPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - PartialReplyPrinterChangeNotification
---

## -description

The print spooler's **PartialReplyPrinterChangeNotification** function allows a print provider to update the spooler's database of printer changes associated with a notification handle.

## -parameters

### -param hPrinter

Caller-supplied handle. This handle must have been previously received as the *hNotify* input to the print provider's [FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification) function.

### -param pDataSrc

Caller-supplied pointer to a PRINTER_NOTIFY_INFO_DATA structure (described in the Microsoft Windows SDK documentation). Can be **NULL**. For more information, see the following Remarks section.

## -returns

If the operation succeeds, the function returns **TRUE**. Otherwise the function returns **FALSE**. The caller can obtain an error code by calling **GetLastError**.

## -remarks

For the specified notification handle, the spooler's **PartialReplyPrinterChangeNotification** function adds the contents of the specified PRINTER_NOTIFY_INFO_DATA structure to the array within the spooler's stored PRINTER_NOTIFY_INFO structure. (These structures are described in the Windows SDK documentation.)

Calling **PartialReplyPrinterChangeNotification** does not cause the spooler to notify the application that changes have occurred. If the print provider's [FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification) function did not set the PRINTER_NOTIFY_STATUS_POLL flag, the provider must call [ReplyPrinterChangeNotification](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-replyprinterchangenotification) to cause the application to be notified.

If *pInfoDataSrc* is **NULL**, all stored information associated with the specified handle is deleted from the spooler. The function accomplishes this deletion by freeing all buffers associated with *pBuf* members of PRINTER_NOTIFY_INFO_DATA structures belonging to the specified handle. The function then sets the PRINTER_NOTIFY_INFO_DISCARDED flag in the stored PRINTER_NOTIFY_INFO structure.

For additional information, see [Supporting Printer Change Notifications](/windows-hardware/drivers/print/supporting-printer-change-notifications).

## -see-also

[FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification)

[ReplyPrinterChangeNotification](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-replyprinterchangenotification)
