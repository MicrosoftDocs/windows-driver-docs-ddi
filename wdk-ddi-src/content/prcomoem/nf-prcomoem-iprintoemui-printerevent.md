---
UID: NF:prcomoem.IPrintOemUI.PrinterEvent
title: IPrintOemUI::PrinterEvent (prcomoem.h)
description: The IPrintOemUI::PrinterEvent method allows a user interface plug-in to process printer events.
old-location: print\iprintoemui_printerevent.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemUI::PrinterEvent"]
ms.keywords: IPrintOemUI interface [Print Devices],PrinterEvent method, IPrintOemUI.PrinterEvent, IPrintOemUI::PrinterEvent, PrinterEvent, PrinterEvent method [Print Devices], PrinterEvent method [Print Devices],IPrintOemUI interface, prcomoem/IPrintOemUI::PrinterEvent, print.iprintoemui_printerevent, print_unidrv-pscript_ui_87a42746-bb3f-494a-a647-8b111e2b0e09.xml
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUI::PrinterEvent
 - prcomoem/IPrintOemUI::PrinterEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemUI.PrinterEvent
---

# IPrintOemUI::PrinterEvent


## -description

The <code>IPrintOemUI::PrinterEvent</code> method allows a user interface plug-in to process printer events.

## -parameters

### -param pPrinterName

Caller-supplied pointer to a NULL-terminated printer name string. The string can identify a local printer ("<i>PrinterName</i>") or remote printer ("\\<i>Machine</i>\\<i>PrinterName</i>").

### -param iDriverEvent

Caller-supplied value identifying the event that has occurred. For a list of valid values, see <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent">DrvPrinterEvent</a>.

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

A user interface plug-in's <code>IPrintOemUI::PrinterEvent</code> method performs the same types of operations as the <b>DrvPrinterEvent</b> function that is exported by user-mode printer interface DLLs. For information about printer events and how they should be processed, see the description of the <a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent">DrvPrinterEvent</a> function.

If you provide a user interface plug-in, the printer driver's <b>DrvPrinterEvent</b> function calls the <code>IPrintOemUI::PrinterEvent</code> method. The <b>DrvPrinterEvent</b> function performs its own processing for the specified event, and then calls the <code>IPrintOemUI::PrinterEvent</code> method to handle additional processing of the event.

If <code>IPrintOemUI::PrinterEvent</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent">DrvPrinterEvent</a>



<a href="/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>
