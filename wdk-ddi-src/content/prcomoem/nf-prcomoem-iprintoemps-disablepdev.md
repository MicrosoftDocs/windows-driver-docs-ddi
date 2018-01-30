---
UID: NF:prcomoem.IPrintOemPS.DisablePDEV
title: IPrintOemPS::DisablePDEV method
author: windows-driver-content
description: The IPrintOemPS::DisablePDEV method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its IPrintOemPS::EnablePDEV method.
old-location: print\iprintoemps_disablepdev.htm
old-project: print
ms.assetid: 131a3113-1d65-44e7-8752-bf4cdc20129d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemPS interface [Print Devices], DisablePDEV method, prcomoem/IPrintOemPS::DisablePDEV, IPrintOemPS::DisablePDEV, print.iprintoemps_disablepdev, IPrintOemPS, DisablePDEV method [Print Devices], IPrintOemPS interface, DisablePDEV, print_unidrv-pscript_rendering_7adde157-af87-49c1-80b0-e419c84a12a4.xml, DisablePDEV method [Print Devices]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prcomoem.h
apiname:
-	IPrintOemPS.DisablePDEV
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS::DisablePDEV method


## -description


The <code>IPrintOemPS::DisablePDEV</code> method allows a rendering plug-in for Pscript5 to delete the private PDEV structure that was allocated by its <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a> method.


## -syntax


````
STDMETHOD DisablePDEV(
   PDEVOBJ pdevobj
);
````


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


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


The <code>IPrintOemPS::DisablePDEV</code> method performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to delete the private PDEV structure that is pointed to by the DEVOBJ structure's <b>pdevOEM</b> member. This PDEV structure is one that was allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553215">IPrintOemPS::EnablePDEV</a> method.


