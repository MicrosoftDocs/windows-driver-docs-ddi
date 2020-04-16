---
UID: NF:winsplp.RouterAllocPrinterNotifyInfo
title: RouterAllocPrinterNotifyInfo function (winsplp.h)
description: The print spooler's RouterAllocPrinterNotifyInfo function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures.
old-location: print\routerallocprinternotifyinfo.htm
tech.root: print
ms.assetid: 319bee1b-c319-4c95-8343-edb9b08e6d6c
ms.date: 04/20/2018
keywords: ["RouterAllocPrinterNotifyInfo function"]
ms.keywords: RouterAllocPrinterNotifyInfo, RouterAllocPrinterNotifyInfo function [Print Devices], print.routerallocprinternotifyinfo, spoolfnc_036587a9-424d-4169-8c90-7de6165a003d.xml, winsplp/RouterAllocPrinterNotifyInfo
f1_keywords:
 - "winsplp/RouterAllocPrinterNotifyInfo"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Spoolss.dll
api_name:
- RouterAllocPrinterNotifyInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# RouterAllocPrinterNotifyInfo function


## -description


The print spooler's <code>RouterAllocPrinterNotifyInfo</code> function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures. (These structures are described in the Microsoft Windows SDK documentation.)


## -parameters




### -param cPrinterNotifyInfoData

Caller-supplied number specifying size of the PRINTER_NOTIFY_INFO_DATA structure array to be allocated.


## -returns



The function returns a pointer to the allocated PRINTER_NOTIFY_INFO structure.




## -remarks



Print providers should call <code>RouterAllocPrinterNotifyInfo</code> to allocate the PRINTER_NOTIFY_INFO structure and the PRINTER_NOTIFY_INFO_DATA structure array that the provider's <a href="https://docs.microsoft.com/previous-versions/ff561930(v=vs.85)">RefreshPrinterChangeNotification</a> function must supply.

The <code>RouterAllocPrinterNotifyInfo</code> function initializes the PRINTER_NOTIFY_INFO structure's <b>Version</b> member to the current version of the spooler's notification implementation. It initializes the structure's <b>Flags</b> and <b>Count</b> members to zero, regardless of the number specified for <i>cPrinterNotifyInfoData</i>.

Print providers should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-appendprinternotifyinfodata">AppendPrinterNotifyInfoData</a> to fill in members of the PRINTER_NOTIFY_INFO_DATA structure array.

If <code>RefreshPrinterChangeNotification</code> executes successfully and returns the allocated structures to the caller, you should assume that the caller will deallocate structure memory. However, if <code>RefreshPrinterChangeNotification</code> encounters an error it should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreeprinternotifyinfo">RouterFreePrinterNotifyInfo</a> to deallocate the memory.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/supporting-printer-change-notifications">Supporting Printer Change Notifications</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-appendprinternotifyinfodata">AppendPrinterNotifyInfoData</a>



<a href="https://docs.microsoft.com/previous-versions/ff561930(v=vs.85)">RefreshPrinterChangeNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerfreeprinternotifyinfo">RouterFreePrinterNotifyInfo</a>
 

 

