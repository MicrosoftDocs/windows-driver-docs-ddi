---
UID: NF:prcomoem.IPrintCoreUI2.DrvUpdateUISetting
title: IPrintCoreUI2::DrvUpdateUISetting (prcomoem.h)
description: The IPrintCoreUI2::DrvUpdateUISetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.
old-location: print\iprintcoreui2_drvupdateuisetting.htm
tech.root: print
ms.assetid: 64cbb304-51f6-4db4-93cb-a64ea5e03599
ms.date: 04/20/2018
ms.keywords: DrvUpdateUISetting, DrvUpdateUISetting method [Print Devices], DrvUpdateUISetting method [Print Devices],IPrintCoreUI2 interface, IPrintCoreUI2 interface [Print Devices],DrvUpdateUISetting method, IPrintCoreUI2.DrvUpdateUISetting, IPrintCoreUI2::DrvUpdateUISetting, prcomoem/IPrintCoreUI2::DrvUpdateUISetting, print.iprintcoreui2_drvupdateuisetting, print_unidrv-pscript_ui_47ba2d93-a51d-4140-8932-9c4caee1ca21.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintCoreUI2.DrvUpdateUISetting"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Prcomoem.h
api_name:
- IPrintCoreUI2.DrvUpdateUISetting
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2::DrvUpdateUISetting


## -description


The <code>IPrintCoreUI2::DrvUpdateUISetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.


## -parameters




### -param pci

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure. 


### -param pOptItem

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structure describing a user interface option item.


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
<tr>
<td>
OEMCUIP_PRNPROP 

</td>
<td>
The supplied option item belongs to the Device Settings page of the printer property sheet. 

</td>
</tr>
</table>
 


## -returns



This method must return one of the following values.

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



This method is inherited from the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemdriverui-com-interface">IPrintOemDriverUI COM Interface</a>, and can be called only by Windows XP Pscript5 UI plug-ins that do not fully replace the core driver's standard UI pages, and is supported during the UI plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines. When this method is supported, it has the same behavior as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a>. When it is not supported, this method should return E_NOTIMPL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemdriverui-drvupdateuisetting">IPrintOemDriverUI::DrvUpdateUISetting</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>
 

 

