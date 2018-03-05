---
UID: NF:winsplp.ReplyPrinterChangeNotification
title: ReplyPrinterChangeNotification function
author: windows-driver-content
description: The print spooler's ReplyPrinterChangeNotification function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred.
old-location: print\replyprinterchangenotification.htm
old-project: print
ms.assetid: 0b5378fa-ab1d-453f-b976-f6cd0d4247de
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ReplyPrinterChangeNotification, ReplyPrinterChangeNotification function [Print Devices], print.replyprinterchangenotification, spoolfnc_524073df-9320-46d6-b4fe-6d3b73ccbe5b.xml, winsplp/ReplyPrinterChangeNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	ReplyPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ReplyPrinterChangeNotification function


## -description


The print spooler's <code>ReplyPrinterChangeNotification</code> function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred.


## -syntax


````
BOOL ReplyPrinterChangeNotification(
  _In_      HANDLE hNotify,
            DWORD  fdwFlags,
  _Out_opt_ PDWORD pdwResult,
  _In_opt_  PVOID  pPrinterNotifyInfo
);
````


## -parameters




### -param hPrinter

TBD


### -param fdwChangeFlags

TBD


### -param pdwResult [out, optional]

Optional. If not <b>NULL</b>, it receives spooler-supplied PRINTER_NOTIFY_INFO-prefixed flags indicating results of updating the supplied information.


### -param pPrinterNotifyInfo [in, optional]

Optional. Caller-supplieid address of a PRINTER_NOTIFY_INFO structure (described in the Windows SDK documentation). Can be <b>NULL</b> if no new notification information is being added.


#### - hNotify [in]

Caller-supplied handle. This handle must have been previously received as the <i>hNotify</i> input to the print provider's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548837">FindFirstPrinterChangeNotification</a> function.


#### - fdwFlags

One or more caller-supplied PRINTER_CHANGE_-prefixed flags, listed in the Microsoft Windows SDK documentation's description of <b>FindNextPrinterChangeNotification</b>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>. The caller can obtain an error code by calling <b>GetLastError</b>.




## -remarks



Print providers that do not support polling (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548837">FindFirstPrinterChangeNotification</a>) must notify the spooler of the occurrence of any events represented by the PRINTER_CHANGE_-prefixed flags received by the provider's <b>FindFirstPrinterChangeNotification</b> function. When an event occurs, the print provider can call <code>ReplyPrinterChangeNotification</code> to inform the spooler of the event and to supply information associated with the event. The spooler keeps track of this event information, for each notification handle, and delivers the information to an application when the application calls <b>FindNextPrinterChangeNotification</b> (described in the Windows SDK documentation).

When a print provider calls <code>ReplyPrinterChangeNotification</code>, it must identify the event that has occurred by setting a PRINTER_CHANGE_-prefixed flag in <i>fwdFlags</i> or by using <i>pPrinterNotifyInfo</i> to return a PRINTER_NOTIFY_INFO structure. (Use the flags listed in the Windows SDK documentation's description of <b>FindNextPrinterChangeNotification</b>--not the flags listed in the Windows SDK documentation's description of <b>FindFirstPrinterChangeNotification</b>.)

Calling <code>ReplyPrinterChangeNotification</code> causes the spooler to signal the client application that a print queue event has occurred. This happens even if the provider supplies <b>NULL</b> for <i>pPrinterNotifyInfo</i>. To update the spooler's record of print queue changes without causing the client to be notified, use <a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a>. It is common to call <b>PartialReplyPrinterChangeNotification</b> several times to update the spooler's database, then to call <code>ReplyPrinterChangeNotification</code> to notify the client that changes have occurred.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.




## -see-also

<a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548837">FindFirstPrinterChangeNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ReplyPrinterChangeNotification function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

