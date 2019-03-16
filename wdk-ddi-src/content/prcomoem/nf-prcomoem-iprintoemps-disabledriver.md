---
UID: NF:prcomoem.IPrintOemPS.DisableDriver
title: IPrintOemPS::DisableDriver (prcomoem.h)
description: The IPrintOemPS::DisableDriver method allows a rendering plug-in for Pscript to free resources that were allocated by the plug-in's IPrintOemPS::EnableDriver method.
old-location: print\iprintoemps_disabledriver.htm
tech.root: print
ms.assetid: 4fa25706-dc79-45fd-a805-7b9d110213ed
ms.date: 04/20/2018
ms.keywords: DisableDriver, DisableDriver method [Print Devices], DisableDriver method [Print Devices],IPrintOemPS interface, IPrintOemPS interface [Print Devices],DisableDriver method, IPrintOemPS.DisableDriver, IPrintOemPS::DisableDriver, prcomoem/IPrintOemPS::DisableDriver, print.iprintoemps_disabledriver, print_unidrv-pscript_rendering_f8c7413c-104b-4509-9909-89e97acc0069.xml
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
- Prcomoem.h
api_name:
- IPrintOemPS.DisableDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPS::DisableDriver


## -description


The <code>IPrintOemPS::DisableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> to free resources that were allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a> method.


## -parameters






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



The <code>IPrintOemPS::DisableDriver</code> method, provided by rendering plug-ins for Pscript5, performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556196">DrvDisableDriver</a> function that is exported by Pscript5's printer graphics DLL.

<code>IPrintOemPS::DisableDriver</code> and <b>IPrintOemPS::EnableDriver</b> must be implemented as a pair. If you implement one, you must implement the other. For more information, see the Remarks section in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a>. 

This is the last <b>IPrintOemPS</b> interface method that is called before the rendering plug-in is unloaded.



