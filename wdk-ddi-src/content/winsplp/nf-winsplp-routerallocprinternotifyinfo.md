---
UID: NF:winsplp.RouterAllocPrinterNotifyInfo
title: RouterAllocPrinterNotifyInfo function
author: windows-driver-content
description: The print spooler's RouterAllocPrinterNotifyInfo function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures.
old-location: print\routerallocprinternotifyinfo.htm
old-project: print
ms.assetid: 319bee1b-c319-4c95-8343-edb9b08e6d6c
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: spoolfnc_036587a9-424d-4169-8c90-7de6165a003d.xml, winsplp/RouterAllocPrinterNotifyInfo, print.routerallocprinternotifyinfo, RouterAllocPrinterNotifyInfo, RouterAllocPrinterNotifyInfo function [Print Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Spoolss.dll
apiname:
-	RouterAllocPrinterNotifyInfo
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# RouterAllocPrinterNotifyInfo function


## -description


The print spooler's <code>RouterAllocPrinterNotifyInfo</code> function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures. (These structures are described in the Microsoft Windows SDK documentation.)


## -syntax


````
PPRINTER_NOTIFY_INFO RouterAllocPrinterNotifyInfo(
   DWORD cPrinterNotifyInfoData
);
````


## -parameters




### -param cPrinterNotifyInfoData

Caller-supplied number specifying size of the PRINTER_NOTIFY_INFO_DATA structure array to be allocated.


## -returns



The function returns a pointer to the allocated PRINTER_NOTIFY_INFO structure.




## -remarks



Print providers should call <code>RouterAllocPrinterNotifyInfo</code> to allocate the PRINTER_NOTIFY_INFO structure and the PRINTER_NOTIFY_INFO_DATA structure array that the provider's <a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a> function must supply.

The <code>RouterAllocPrinterNotifyInfo</code> function initializes the PRINTER_NOTIFY_INFO structure's <b>Version</b> member to the current version of the spooler's notification implementation. It initializes the structure's <b>Flags</b> and <b>Count</b> members to zero, regardless of the number specified for <i>cPrinterNotifyInfoData</i>.

Print providers should call <a href="..\winsplp\nf-winsplp-appendprinternotifyinfodata.md">AppendPrinterNotifyInfoData</a> to fill in members of the PRINTER_NOTIFY_INFO_DATA structure array.

If <code>RefreshPrinterChangeNotification</code> executes successfully and returns the allocated structures to the caller, you should assume that the caller will deallocate structure memory. However, if <code>RefreshPrinterChangeNotification</code> encounters an error it should call <a href="..\winsplp\nf-winsplp-routerfreeprinternotifyinfo.md">RouterFreePrinterNotifyInfo</a> to deallocate the memory.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.




## -see-also

<a href="..\winsplp\nf-winsplp-routerfreeprinternotifyinfo.md">RouterFreePrinterNotifyInfo</a>



<a href="..\winsplp\nf-winsplp-appendprinternotifyinfodata.md">AppendPrinterNotifyInfoData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RouterAllocPrinterNotifyInfo function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

