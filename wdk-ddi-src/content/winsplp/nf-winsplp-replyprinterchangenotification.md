---
UID: NF:winsplp.ReplyPrinterChangeNotification
title: ReplyPrinterChangeNotification function (winsplp.h)
description: The print spooler's ReplyPrinterChangeNotification function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred.
tech.root: print
ms.date: 07/27/2022
keywords: ["ReplyPrinterChangeNotification function"]
ms.keywords: ReplyPrinterChangeNotification, ReplyPrinterChangeNotification function [Print Devices], print.replyprinterchangenotification, spoolfnc_524073df-9320-46d6-b4fe-6d3b73ccbe5b.xml, winsplp/ReplyPrinterChangeNotification
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
 - ReplyPrinterChangeNotification
 - winsplp/ReplyPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - ReplyPrinterChangeNotification
---

## -description

The print spooler's **ReplyPrinterChangeNotification** function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred.

## -parameters

### -param hPrinter

Caller-supplied handle. This handle must have been previously received as the *hNotify* input to the print provider's [FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification) function.

### -param fdwChangeFlags

One or more caller-supplied PRINTER_CHANGE_-prefixed flags, listed in the Microsoft Windows SDK documentation's description of **FindNextPrinterChangeNotification**.

### -param pdwResult [out, optional]

Optional. If not **NULL**, it receives spooler-supplied PRINTER_NOTIFY_INFO-prefixed flags indicating results of updating the supplied information.

### -param pPrinterNotifyInfo [in, optional]

Optional. Caller-supplieid address of a PRINTER_NOTIFY_INFO structure (described in the Windows SDK documentation). Can be **NULL** if no new notification information is being added.

## -returns

If the operation succeeds, the function returns **TRUE**. Otherwise the function returns **FALSE**. The caller can obtain an error code by calling **GetLastError**.

## -remarks

Print providers that do not support polling (see [FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification)) must notify the spooler of the occurrence of any events represented by the PRINTER_CHANGE_-prefixed flags received by the provider's **FindFirstPrinterChangeNotification** function. When an event occurs, the print provider can call **ReplyPrinterChangeNotification** to inform the spooler of the event and to supply information associated with the event. The spooler keeps track of this event information, for each notification handle, and delivers the information to an application when the application calls **FindNextPrinterChangeNotification** (described in the Windows SDK documentation).

When a print provider calls **ReplyPrinterChangeNotification**, it must identify the event that has occurred by setting a PRINTER_CHANGE_-prefixed flag in *fwdFlags* or by using *pPrinterNotifyInfo* to return a PRINTER_NOTIFY_INFO structure. (Use the flags listed in the Windows SDK documentation's description of **FindNextPrinterChangeNotification**--not the flags listed in the Windows SDK documentation's description of **FindFirstPrinterChangeNotification**.)

Calling **ReplyPrinterChangeNotification** causes the spooler to signal the client application that a print queue event has occurred. This happens even if the provider supplies **NULL** for *pPrinterNotifyInfo*. To update the spooler's record of print queue changes without causing the client to be notified, use [PartialReplyPrinterChangeNotification](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-partialreplyprinterchangenotification). It is common to call **PartialReplyPrinterChangeNotification** several times to update the spooler's database, then to call **ReplyPrinterChangeNotification** to notify the client that changes have occurred.

For additional information, see [Supporting Printer Change Notifications](/windows-hardware/drivers/print/supporting-printer-change-notifications).

## -see-also

[FindFirstPrinterChangeNotification](/windows-hardware/drivers/ddi/winspool/nf-winspool-findfirstprinterchangenotification)

[PartialReplyPrinterChangeNotification](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-partialreplyprinterchangenotification)
