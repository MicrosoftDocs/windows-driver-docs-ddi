---
UID: NF:prcomoem.IPrintOemDriverUI.DrvUpdateUISetting
title: IPrintOemDriverUI::DrvUpdateUISetting method
author: windows-driver-content
description: The IPrintOemDriverUI::DrvUpdateUISetting method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can notify the driver of a modified user interface option.
old-location: print\iprintoemdriverui_drvupdateuisetting.htm
old-project: print
ms.assetid: f5dec76e-16ad-4df0-b3c9-f0cbfb9b8c41
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemDriverUI, IPrintOemDriverUI::DrvUpdateUISetting, DrvUpdateUISetting
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
req.alt-api: IPrintOemDriverUI.DrvUpdateUISetting
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverUI::DrvUpdateUISetting method



## -description
The <code>IPrintOemDriverUI::DrvUpdateUISetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can notify the driver of a modified user interface option.



## -syntax

````
HRESULT DrvUpdateUISetting(
   PVOID pci,
   PVOID pOptItem,
   DWORD dwPreviousSelection,
   DWORD dwMode
);
````


## -parameters

### -param pci 

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure.


### -param pOptItem 

Caller-supplied pointer to an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure describing a user interface option item.


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
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
If you are providing a user interface plug-in that implements the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> method or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> method, you typically also supply a <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function to handle user modifications. This callback function must call <code>IPrintOemDriverUI::DrvUpdateUISetting</code> to inform the driver when the value associated with a user interface setting has been modified, if the value is stored in the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure (instead of the plug-in's private DEVMODEW members ) or in registry keys.

The value specified for <i>dwMode</i> should be based on which method specified the callback function.</p>