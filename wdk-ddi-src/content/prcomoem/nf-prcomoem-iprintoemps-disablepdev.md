---
UID: NF:prcomoem.IPrintOemPS.DisablePDEV
title: IPrintOemPS::DisablePDEV (prcomoem.h)
description: The IPrintOemPS::DisablePDEV method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its IPrintOemPS::EnablePDEV method.
old-location: print\iprintoemps_disablepdev.htm
tech.root: print
ms.assetid: 131a3113-1d65-44e7-8752-bf4cdc20129d
ms.date: 04/20/2018
ms.keywords: DisablePDEV, DisablePDEV method [Print Devices], DisablePDEV method [Print Devices],IPrintOemPS interface, IPrintOemPS interface [Print Devices],DisablePDEV method, IPrintOemPS.DisablePDEV, IPrintOemPS::DisablePDEV, prcomoem/IPrintOemPS::DisablePDEV, print.iprintoemps_disablepdev, print_unidrv-pscript_rendering_7adde157-af87-49c1-80b0-e419c84a12a4.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemPS.DisablePDEV"
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
- IPrintOemPS.DisablePDEV
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPS::DisablePDEV


## -description


The <code>IPrintOemPS::DisablePDEV</code> method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a> method.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


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



The <code>IPrintOemPS::DisablePDEV</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvdisablepdev">DrvDisablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to delete the private PDEV structure that is pointed to by the DEVOBJ structure's <b>pdevOEM</b> member. This PDEV structure is one that was allocated by the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-enablepdev">IPrintOemPS::EnablePDEV</a> method.



