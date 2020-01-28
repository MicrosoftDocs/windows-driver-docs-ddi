---
UID: NF:prcomoem.IPrintOemUI.DevMode
title: IPrintOemUI::DevMode (prcomoem.h)
description: The IPrintOemUI::DevMode method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.
old-location: print\iprintoemui_devmode.htm
tech.root: print
ms.assetid: decc76c4-1973-41c5-9091-6dc5b9ccd30d
ms.date: 04/20/2018
ms.keywords: DevMode, DevMode method [Print Devices], DevMode method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DevMode method, IPrintOemUI.DevMode, IPrintOemUI::DevMode, prcomoem/IPrintOemUI::DevMode, print.iprintoemui_devmode, print_unidrv-pscript_ui_3d5344ac-bacd-499b-87f7-c8e1b7f0e174.xml
f1_keywords:
 - "prcomoem/IPrintOemUI.DevMode"
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
- IPrintOemUI.DevMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::DevMode


## -description


The <code>IPrintOemUI::DevMode</code> method, provided by user interface plug-ins, performs operations on the plug-in's private DEVMODEW members.


## -parameters




### -param dwMode

Caller-supplied constant. See the following Remarks section.


### -param pOemDMParam

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemdmparam">OEMDMPARAM</a> structure.


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



User interface plug-ins must implement a <code>IPrintOemUI::DevMode</code> method if they define private <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure members. The method's purpose is to define, validate, or convert (from one version to another) the contents of the private DEVMODEW structure members.

A private DEVMODEW section must be prefaced by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oem_dmextraheader">OEM_DMEXTRAHEADER</a> structure.

The <code>IPrintOemUI::DevMode</code> method must perform the operation indicated by its <i>dwMode</i> value. Each time <code>IPrintOemUI::DevMode</code> is called, <i>dwMode</i> contains one of the following constants, which are listed in the order they are received:






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemui">IPrintOemUI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">IPrintOemUni::DevMode</a>
 

 

