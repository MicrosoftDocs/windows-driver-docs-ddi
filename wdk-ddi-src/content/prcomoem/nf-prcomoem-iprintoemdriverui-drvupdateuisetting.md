---
UID: NF:prcomoem.IPrintOemDriverUI.DrvUpdateUISetting
title: IPrintOemDriverUI::DrvUpdateUISetting (prcomoem.h)
description: The IPrintOemDriverUI::DrvUpdateUISetting method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can notify the driver of a modified user interface option.
old-location: print\iprintoemdriverui_drvupdateuisetting.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintOemDriverUI::DrvUpdateUISetting"]
ms.keywords: DrvUpdateUISetting, DrvUpdateUISetting method [Print Devices], DrvUpdateUISetting method [Print Devices],IPrintOemDriverUI interface, IPrintOemDriverUI interface [Print Devices],DrvUpdateUISetting method, IPrintOemDriverUI.DrvUpdateUISetting, IPrintOemDriverUI::DrvUpdateUISetting, prcomoem/IPrintOemDriverUI::DrvUpdateUISetting, print.iprintoemdriverui_drvupdateuisetting, print_unidrv-pscript_ui_7a403e81-0021-463c-954c-659dd8c578b0.xml
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
 - IPrintOemDriverUI::DrvUpdateUISetting
 - prcomoem/IPrintOemDriverUI::DrvUpdateUISetting
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemDriverUI::DrvUpdateUISetting
---

# IPrintOemDriverUI::DrvUpdateUISetting


## -description

The <code>IPrintOemDriverUI::DrvUpdateUISetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can notify the driver of a modified user interface option.

## -parameters

### -param pci

Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.

### -param pOptItem

Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure describing a user interface option item.

### -param dwPreviousSelection

Not used.

### -param dwMode

Caller-supplied integer constant indicating to which property sheet page the supplied option item belongs. The following constants are valid.

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
OEMCUIP_DOCPROP

</td>
<td>
The supplied option item belongs to the Advanced page of the document property sheet.

</td>
</tr>
<tr>
<td>
OEMCUIP_PRNPROP

</td>
<td>
The supplied option item belongs to the Device Settings page of the printer property sheet.

</td>
</tr>
</table>
 

For more information, see the following Remarks section.

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

If you are providing a user interface plug-in that implements the <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> method or the <a href="/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> method, you typically also supply a <a href="/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>-typed callback function to handle user modifications. This callback function must call <code>IPrintOemDriverUI::DrvUpdateUISetting</code> to inform the driver when the value associated with a user interface setting has been modified, if the value is stored in the driver's <a href="/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure (instead of the plug-in's private DEVMODEW members ) or in registry keys.

The value specified for <i>dwMode</i> should be based on which method specified the callback function.

