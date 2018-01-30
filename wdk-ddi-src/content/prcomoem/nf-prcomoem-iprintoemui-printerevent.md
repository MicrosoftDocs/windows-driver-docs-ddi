---
UID: NF:prcomoem.IPrintOemUI.PrinterEvent
title: IPrintOemUI::PrinterEvent method
author: windows-driver-content
description: The IPrintOemUI::PrinterEvent method allows a user interface plug-in to process printer events.
old-location: print\iprintoemui_printerevent.htm
old-project: print
ms.assetid: 214ea4d8-3bf9-4248-8bfa-7180635769be
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemUI, IPrintOemUI interface [Print Devices], PrinterEvent method, PrinterEvent method [Print Devices], IPrintOemUI interface, PrinterEvent, prcomoem/IPrintOemUI::PrinterEvent, print_unidrv-pscript_ui_87a42746-bb3f-494a-a647-8b111e2b0e09.xml, IPrintOemUI::PrinterEvent, print.iprintoemui_printerevent, PrinterEvent method [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemUI.PrinterEvent
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI::PrinterEvent method


## -description


The <code>IPrintOemUI::PrinterEvent</code> method allows a user interface plug-in to process printer events.


## -syntax


````
HRESULT PrinterEvent(
   PWSTR  pPrinterName,
   INT    iDriverEvent,
   DWORD  dwFlags,
   LPARAM lParam
);
````


## -parameters




### -param pPrinterName

Caller-supplied pointer to a NULL-terminated printer name string. The string can identify a local printer ("<i>PrinterName</i>") or remote printer ("\\<i>Machine</i>\<i>PrinterName</i>").


### -param iDriverEvent

Caller-supplied value identifying the event that has occurred. For a list of valid values, see <a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a>.


### -param dwFlags

Caller-supplied flags. For a list of valid flags, see <b>DrvPrinterEvent</b>.


### -param lParam

Caller-supplied event-specific parameter. For more information, see <b>DrvPrinterEvent</b>.


## -returns


The method must return one of the following values.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table> 



## -remarks


A user interface plug-in's <code>IPrintOemUI::PrinterEvent</code> method performs the same types of operations as the <b>DrvPrinterEvent</b> function that is exported by user-mode printer interface DLLs. For information about printer events and how they should be processed, see the description of the <a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a> function.

If you provide a user interface plug-in, the printer driver's <b>DrvPrinterEvent</b> function calls the <code>IPrintOemUI::PrinterEvent</code> method. The <b>DrvPrinterEvent</b> function performs its own processing for the specified event, and then calls the <code>IPrintOemUI::PrinterEvent</code> method to handle additional processing of the event.

If <code>IPrintOemUI::PrinterEvent</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.



## -see-also

<a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUI::PrinterEvent method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

