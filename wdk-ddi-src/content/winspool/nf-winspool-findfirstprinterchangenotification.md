---
UID: NF:winspool.FindFirstPrinterChangeNotification
title: FindFirstPrinterChangeNotification function (winspool.h)
description: The FindFirstPrinterChangeNotification function informs the provider that an application has requested notification when a specified set of events occur.
tech.root: print
ms.date: 04/20/2022
keywords: ["FindFirstPrinterChangeNotification function"]
ms.keywords: spoolfnc_cf13c78b-91e2-4d6e-b7be-fda42b3e7588.xml, print.findfirstprinterchangenotification, FindFirstPrinterChangeNotification, winspool/FindFirstPrinterChangeNotification, FindFirstPrinterChangeNotification function [Print Devices]
req.header: winspool.h
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
req.typenames: BIDI_TYPE
f1_keywords:
 - FindFirstPrinterChangeNotification
 - winspool/FindFirstPrinterChangeNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - FindFirstPrinterChangeNotification
---

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

A print provider's **FindFirstPrinterChangeNotification** function informs the provider that an application has requested notification when a specified set of events occur on a specified print queue.

## -parameters

### -param hPrinter

Caller-supplied printer handle, identifying the printer for which event notification is being requested. This handle must have been previously obtained from [OpenPrinter](/windows/win32/printdocs/openprinter).

### -param fdwFilter

Defines the **DWORD** parameter *fdwFilter*.

### -param fdwOptions

Not used.

### -param pPrinterNotifyOptions

Caller-supplied pointer to a PRINTER_NOTIFY_OPTIONS structure (described in the Windows SDK documentation).

## -returns

Returns the print driver handle.

## -remarks

When the spooler calls a print provider's **FindFirstPrinterChangeNotification** function, *pPrinterNotifyOptions* identifies the types of information that the print provider should send to the spooler when one of the specified events occurs.

For a list of the types of notifications an application can request, and for a list of the types of information that can be used to describe an event, see the Windows SDK documentation's description of **FindFirstPrinterChangeNotification**. Types of events for which an application might request notification include adding or deleting a print job or form. Types of information an application might request include job or form parameters.

If the print provider does not request polling, the print provider must supply the types of information identified by *pPrinterNotifyOptions*, by calling [PartialReplyPrinterChangeNotification](..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md) or [ReplyPrinterChangeNotification](..\winsplp\nf-winsplp-replyprinterchangenotification.md).

If the provider does request polling (that is, it sets PRINTER_NOTIFY_STATUS_POLL), it should not call **ReplyPrinterChangeNotification**. Instead, the spooler signals the application at regular intervals.

Both polled and nonpolled print provider must return the current state of all requested information types whenever its [RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85)) function is called.

For additional information, see [Supporting Printer Change Notifications](/windows-hardware/drivers/print/supporting-printer-change-notifications).

## -see-also

[ReplyPrinterChangeNotification](..\winsplp\nf-winsplp-replyprinterchangenotification.md)

[PartialReplyPrinterChangeNotification](..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md)

[RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85))
