---
UID: NF:prcomoem.IPrintOemUni.CommandCallback
title: IPrintOemUni::CommandCallback (prcomoem.h)
description: The IPrintOemUni::CommandCallback method is used to provide dynamically generated printer commands for Unidrv-supported printers.
old-location: print\iprintoemuni_commandcallback.htm
tech.root: print
ms.assetid: e1708017-a546-4770-8ad1-7052b3d4e264
ms.date: 04/20/2018
keywords: ["IPrintOemUni::CommandCallback"]
ms.keywords: CommandCallback, CommandCallback method [Print Devices], CommandCallback method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],CommandCallback method, IPrintOemUni.CommandCallback, IPrintOemUni::CommandCallback, prcomoem/IPrintOemUni::CommandCallback, print.iprintoemuni_commandcallback, print_unidrv-pscript_rendering_edbed499-5cc1-48dc-92cd-dbe70d8560aa.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.CommandCallback"
 - "IPrintOemUni.CommandCallback"
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
- IPrintOemUni.CommandCallback
targetos: Windows
req.typenames: 
---

# IPrintOemUni::CommandCallback


## -description


The <code>IPrintOemUni::CommandCallback</code> method is used to provide dynamically generated printer commands for Unidrv-supported printers.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param dwCallbackID

Caller-supplied value representing the printer command's *<b>CallbackID</b> attribute in the printer's <a href="https://docs.microsoft.com/windows-hardware/drivers/">GPD</a> file. (For more information, see the following Remarks section.)


### -param dwCount

Caller-supplied value representing the number of elements in the array pointed to by <i>pdwParams</i>. Can be 0.


### -param pdwParams

Caller-supplied pointer to an array of DWORD-sized parameters containing values specified by the printer commands *<b>Params</b> attribute in the printer's GPD file. (For more information, see the following Remarks section.) Can be <b>NULL</b>.


### -param piResult 
[out]
Receives a method-supplied result value. See the following Remarks section.


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
The operation failed

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



The <code>IPrintOemUni::CommandCallback</code> method is used by rendering plug-ins to dynamically generate printer commands, for printers that are supported by <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a>.

If you want to dynamically generate a printer command, you must include a *<b>CallbackID</b> attribute and, optionally, a *<b>Params</b> attribute, within the command's *Command entry in the printer's GPD file. For more information see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/dynamically-generated-printer-commands">Dynamically Generated Printer Commands</a>.

When Unidrv calls the <code>IPrintOemUni::CommandCallback</code> method, it supplies the *Command entry's *<b>CallbackID</b> attribute value as the <i>dwCallbackID</i> parameter. It also places the *Command entry's *<b>Params</b> attribute value inside a DWORD array and supplies the array's address as the <i>pParams</i> parameter. The array contains set of Unidrv-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/print/standard-variables">standard variables</a> values, and the <i>dwCount</i> parameter specifies the number of parameters contained in the array. For more information about the attributes see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/command-attributes">Command Attributes</a>.

The method should use the <i>dwCallbackID</i> parameter value to determine which command to process. For each supported command, the method must be aware of which, if any, standard variables have been specified by the *Command entry's *<b>Params</b> attribute, and in which order.

The method is responsible for constructing a printer command, and then sending the command to the print spooler by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> method.

The value supplied for <i>piResult</i> should always return zero unless the method is processing a cursor command. For <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cursor-commands">cursor commands</a> that move the cursor in either the <i>x</i> or <i></i> direction, the method should return the new cursor position.

The <code>IPrintOemUni::CommandCallback</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "CommandCallback" as input.



