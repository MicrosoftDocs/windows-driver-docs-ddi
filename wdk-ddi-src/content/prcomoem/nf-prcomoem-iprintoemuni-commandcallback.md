---
UID: NF:prcomoem.IPrintOemUni.CommandCallback
title: IPrintOemUni::CommandCallback (prcomoem.h)
description: The IPrintOemUni::CommandCallback method is used to provide dynamically generated printer commands for Unidrv-supported printers.
old-location: print\iprintoemuni_commandcallback.htm
tech.root: print
ms.assetid: e1708017-a546-4770-8ad1-7052b3d4e264
ms.date: 04/20/2018
ms.keywords: CommandCallback, CommandCallback method [Print Devices], CommandCallback method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],CommandCallback method, IPrintOemUni.CommandCallback, IPrintOemUni::CommandCallback, prcomoem/IPrintOemUni::CommandCallback, print.iprintoemuni_commandcallback, print_unidrv-pscript_rendering_edbed499-5cc1-48dc-92cd-dbe70d8560aa.xml
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::CommandCallback


## -description


The <code>IPrintOemUni::CommandCallback</code> method is used to provide dynamically generated printer commands for Unidrv-supported printers.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.


### -param dwCallbackID

Caller-supplied value representing the printer command's *<b>CallbackID</b> attribute in the printer's <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GPD</a> file. (For more information, see the following Remarks section.)


### -param dwCount

Caller-supplied value representing the number of elements in the array pointed to by <i>pdwParams</i>. Can be 0.


### -param pdwParams

Caller-supplied pointer to an array of DWORD-sized parameters containing values specified by the printer commands *<b>Params</b> attribute in the printer's GPD file. (For more information, see the following Remarks section.) Can be <b>NULL</b>.


### -param piResult [out]

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



The <code>IPrintOemUni::CommandCallback</code> method is used by rendering plug-ins to dynamically generate printer commands, for printers that are supported by <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a>.

If you want to dynamically generate a printer command, you must include a *<b>CallbackID</b> attribute and, optionally, a *<b>Params</b> attribute, within the command's *Command entry in the printer's GPD file. For more information see <a href="https://msdn.microsoft.com/ba395716-6906-4f23-a050-79d808ccd44b">Dynamically Generated Printer Commands</a>.

When Unidrv calls the <code>IPrintOemUni::CommandCallback</code> method, it supplies the *Command entry's *<b>CallbackID</b> attribute value as the <i>dwCallbackID</i> parameter. It also places the *Command entry's *<b>Params</b> attribute value inside a DWORD array and supplies the array's address as the <i>pParams</i> parameter. The array contains set of Unidrv-defined <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a> values, and the <i>dwCount</i> parameter specifies the number of parameters contained in the array. For more information about the attributes see <a href="https://msdn.microsoft.com/8ce2c668-a130-428e-bf5f-0eab2dcd3fdb">Command Attributes</a>.

The method should use the <i>dwCallbackID</i> parameter value to determine which command to process. For each supported command, the method must be aware of which, if any, standard variables have been specified by the *Command entry's *<b>Params</b> attribute, and in which order.

The method is responsible for constructing a printer command, and then sending the command to the print spooler by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> method.

The value supplied for <i>piResult</i> should always return zero unless the method is processing a cursor command. For <a href="https://msdn.microsoft.com/3ef09c7e-0e88-4236-a4c9-d89eb7ec61cb">cursor commands</a> that move the cursor in either the <i>x</i> or <i></i> direction, the method should return the new cursor position.

The <code>IPrintOemUni::CommandCallback</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "CommandCallback" as input.



