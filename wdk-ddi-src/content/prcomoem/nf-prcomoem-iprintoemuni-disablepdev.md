---
UID: NF:prcomoem.IPrintOemUni.DisablePDEV
title: IPrintOemUni::DisablePDEV (prcomoem.h)
description: The IPrintOemUni::DisablePDEV method allows a rendering plug-in for Unidrv to delete the private PDEV structure that was allocated by its IPrintOemUni::EnablePDEV method.
old-location: print\iprintoemuni_disablepdev.htm
tech.root: print
ms.assetid: bdceeb23-5d4a-4a1c-98b2-014a4126ca5f
ms.date: 04/20/2018
keywords: ["IPrintOemUni::DisablePDEV"]
ms.keywords: DisablePDEV, DisablePDEV method [Print Devices], DisablePDEV method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],DisablePDEV method, IPrintOemUni.DisablePDEV, IPrintOemUni::DisablePDEV, prcomoem/IPrintOemUni::DisablePDEV, print.iprintoemuni_disablepdev, print_unidrv-pscript_rendering_e904ec4d-9153-4427-a98a-1bd4dc381530.xml
f1_keywords:
 - "prcomoem/IPrintOemUni.DisablePDEV"
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
- IPrintOemUni.DisablePDEV
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::DisablePDEV


## -description


The <code>IPrintOemUni::DisablePDEV</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to delete the private PDEV structure that was allocated by its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a> method.


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
</table>
 




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DisablePDEV</code> method.

The <code>IPrintOemUni::DisablePDEV</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvdisablepdev">DrvDisablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to delete the private PDEV structure that is pointed to by the DEVOBJ structure's <b>pdevOEM</b> member. This PDEV structure is one that was allocated by the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-enablepdev">IPrintOemUni::EnablePDEV</a> method.



