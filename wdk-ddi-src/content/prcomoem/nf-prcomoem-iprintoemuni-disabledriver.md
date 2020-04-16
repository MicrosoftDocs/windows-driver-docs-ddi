---
UID: NF:prcomoem.IPrintOemUni.DisableDriver
title: IPrintOemUni::DisableDriver (prcomoem.h)
description: The IPrintOemuNI::DisableDriver method allows a rendering plug-in for Unidrv to free resources that were allocated by the plug-in's IPrintOemUni::EnableDriver method.
old-location: print\iprintoemuni_disabledriver.htm
tech.root: print
ms.assetid: a92d8c2e-52b5-4941-b49e-42e067e56e91
ms.date: 04/20/2018
keywords: ["IPrintOemUni::DisableDriver"]
ms.keywords: DisableDriver, DisableDriver method [Print Devices], DisableDriver method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DisableDriver method, IPrintOemUni.DisableDriver, IPrintOemUni::DisableDriver, prcomoem/IPrintOemUni::DisableDriver, print.iprintoemuni_disabledriver, print_unidrv-pscript_rendering_033d3e0c-4d60-4925-a5b4-1fb47aa42cc9.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.DisableDriver"
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
- IPrintOemUni.DisableDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DisableDriver


## -description


The <code>IPrintOemuNI::DisableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to free resources that were allocated by the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enabledriver">IPrintOemUni::EnableDriver</a> method.


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
</table>
 




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DisableDriver</code> method.

The <code>IPrintOemUni::DisableDriver</code> method, provided by rendering plug-ins for Unidrv, performs the same types of operations as the <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvdisabledriver">DrvDisableDriver</a> function that is exported by Unidrv's printer graphics DLL.

<code>IPrintOemUni::DisableDriver</code> and <b>IPrintOemUni::EnableDriver</b> must be implemented as a pair. If you implement one, you must implement the other. For more information, see the Remarks section in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enabledriver">IPrintOemUni::EnableDriver</a>. 

This is the last <b>IPrintOemUni</b> interface method that is called before the rendering plug-in is unloaded.



