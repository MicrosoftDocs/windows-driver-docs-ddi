---
UID: NF:winspool.FindFirstPrinterChangeNotification
title: FindFirstPrinterChangeNotification function
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\findfirstprinterchangenotification.htm
tech.root: print
ms.assetid: f6d2034a-0906-42ea-a4bd-9cdb1b36c5cf
ms.date: 2/2/2018
ms.keywords: spoolfnc_cf13c78b-91e2-4d6e-b7be-fda42b3e7588.xml, print.findfirstprinterchangenotification, FindFirstPrinterChangeNotification, winspool/FindFirstPrinterChangeNotification, FindFirstPrinterChangeNotification function [Print Devices]
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WinSpool.drv
apiname:
-	FindFirstPrinterChangeNotification
product:
- Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# FindFirstPrinterChangeNotification function


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>A print provider's <b>FindFirstPrinterChangeNotification</b> function informs the provider that an application has requested notification when a specified set of events occur on a specified print queue.


## -syntax


```cpp
BOOL FindFirstPrinterChangeNotification(
   HANDLE hPrinter,
   DWORD  fdwFlags,
   DWORD  fdwOptions,
   HANDLE hNotify,
   PDWORD pfdwStatus,
   PVOID  pPrinterNotifyOptions,
   PVOID  pPrinterNotifyInit
);
```


## -parameters




### -param hPrinter

Caller-supplied printer handle, identifying the printer for which event notification is being requested. This handle must have been previously obtained from OpenPrinter (described in the Microsoft Windows SDK documentation).


### -param fdwFilter




### -param fdwOptions

Not used.


### -param pPrinterNotifyOptions

Caller-supplied pointer to a PRINTER_NOTIFY_OPTIONS structure (described in the Windows SDK documentation).


#### - fdwFlags

One or more caller-supplied PRINTER_CHANGE-prefixed flags. For more information, see the description of <b>FindFirstPrinterChangeNotification</b> in the Windows SDK documentation.


#### - hNotify

Caller-supplied notification handle. This handle must be saved and used as input to <a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a> and <a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a>.


#### - pPrinterNotifyInit

Not used.


#### - pfdwStatus

Caller-supplied pointer to a location to receive provider-specified flags. The following flags are defined.





#### PRINTER_NOTIFY_STATUS_ENDPOINT

If set, the print provider supplies print change notifications, by either the polling or the change notification method. (The notification method is identified by the PRINTER_NOTIFY_STATUS_POLL flag.)





#### PRINTER_NOTIFY_STATUS_POLL

If set, the print application must poll to detect printer changes.

If clear, the print provider notifies the spooler of changes by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>.

(See the following Remarks section.)





#### PRINTER_NOTIFY_STATUS_INFO

Not used.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.




## -remarks



When the spooler calls a print provider's <b>FindFirstPrinterChangeNotification</b> function, <i>fdwFlags</i> identifies the printer events for which notification is being requested. Additionally, <i>pPrinterNotifyOptions</i> identifies the types of information that the print provider should send to the spooler when one of the specified events occurs.

For a list of the types of notifications an application can request, and for a list of the types of information that can be used to describe an event, see the Windows SDK documentation's description of <b>FindFirstPrinterChangeNotification</b>. Types of events for which an application might request notification include adding or deleting a print job or form. Types of information an application might request include job or form parameters.

If the print provider does not request polling (that is, it does not set PRINTER_NOTIFY_STATUS_POLL in <i>pfdwStatus</i>), it must notify the spooler when events identified by <i>pfwFlags</i> occur. The print provider must supply the types of information identified by <i>pPrinterNotifyOptions</i>, by calling <a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a> or <a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a>.

If the provider does request polling (that is, it sets PRINTER_NOTIFY_STATUS_POLL), it should not call <b>ReplyPrinterChangeNotification</b>. Instead, the spooler signals the application at regular intervals.

Both polled and nonpolled print provider must return the current state of all requested information types whenever its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a> function is called.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.




## -see-also

<a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a>



<a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>



 

 


