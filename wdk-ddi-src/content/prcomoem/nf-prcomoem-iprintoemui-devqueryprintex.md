---
UID: NF:prcomoem.IPrintOemUI.DevQueryPrintEx
title: IPrintOemUI::DevQueryPrintEx (prcomoem.h)
description: The IPrintOemUI::DevQueryPrintEx method allows a user interface plug-in to help determine if a print job is printable.
old-location: print\iprintoemui_devqueryprintex.htm
tech.root: print
ms.assetid: a1bc9be3-53ec-4506-a409-94a65d7136e1
ms.date: 04/20/2018
keywords: ["IPrintOemUI::DevQueryPrintEx"]
ms.keywords: DevQueryPrintEx, DevQueryPrintEx method [Print Devices], DevQueryPrintEx method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DevQueryPrintEx method, IPrintOemUI.DevQueryPrintEx, IPrintOemUI::DevQueryPrintEx, prcomoem/IPrintOemUI::DevQueryPrintEx, print.iprintoemui_devqueryprintex, print_unidrv-pscript_ui_64a7a4c1-9478-4710-8d2e-84696b8941b0.xml
f1_keywords:
 - "prcomoem/IPrintOemUI.DevQueryPrintEx"
 - "IPrintOemUI.DevQueryPrintEx"
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
- prcomoem.h
api_name:
- IPrintOemUI.DevQueryPrintEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::DevQueryPrintEx


## -description


The <code>IPrintOemUI::DevQueryPrintEx</code> method allows a user interface plug-in to help determine if a print job is printable.


## -parameters




### -param poemuiobj

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure.


### -param pDQPInfo

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_devqueryprint_info">DEVQUERYPRINT_INFO</a> structure.


### -param pPublicDM

Caller-supplied pointer to a validated <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure.


### -param pOEMDM

Caller-supplied pointer to the user interface plug-in's private DEVMODEW structure members.


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



A user interface plug-in's <code>IPrintOemUI::DevQueryPrintEx</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-devqueryprintex">DevQueryPrintEx</a> function that is exported by user-mode printer interface DLLs. You can use this method to enhance the functionality provided by the <b>DevQueryPrintEx</b> function. Like the <b>DevQueryPrintEx</b> function, the <code>IPrintOemUI::DevQueryPrintEx</code> method's responsibility is to determine if the print job described by the supplied DEVMODEW structure can be printed.

When the driver's <b>DevQueryPrintEx</b> function is called, it checks the DEVMODEW structure, along with the currently selected printer options, to determine if the job is printable. If it is not, the function returns <b>FALSE</b>. If the job appears to be printable, the function calls the <code>IPrintOemUI::DevQueryPrintEx</code> method in each user interface plug-in associated with the driver. If all <code>IPrintOemUI::DevQueryPrintEx</code> methods return S_OK, then <b>DevQueryPrintEx</b> returns <b>TRUE</b>. Thus, a job is not printable unless the <b>DevQueryPrintEx</b> function and all <code>IPrintOemUI::DevQueryPrintEx</code> methods declare it to be printable.

If <code>IPrintOemUI::DevQueryPrintEx</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-devqueryprintex">DevQueryPrintEx</a>
 

 

