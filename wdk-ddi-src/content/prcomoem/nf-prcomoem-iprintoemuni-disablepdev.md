---
UID: NF:prcomoem.IPrintOemUni.DisablePDEV
title: IPrintOemUni::DisablePDEV method
author: windows-driver-content
description: The IPrintOemUni::DisablePDEV method allows a rendering plug-in for Unidrv to delete the private PDEV structure that was allocated by its IPrintOemUni::EnablePDEV method.
old-location: print\iprintoemuni_disablepdev.htm
old-project: print
ms.assetid: bdceeb23-5d4a-4a1c-98b2-014a4126ca5f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemUni interface [Print Devices], DisablePDEV method, print.iprintoemuni_disablepdev, IPrintOemUni, DisablePDEV, IPrintOemUni::DisablePDEV, prcomoem/IPrintOemUni::DisablePDEV, DisablePDEV method [Print Devices], IPrintOemUni interface, print_unidrv-pscript_rendering_e904ec4d-9153-4427-a98a-1bd4dc381530.xml, DisablePDEV method [Print Devices]
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
-	IPrintOemUni.DisablePDEV
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::DisablePDEV method


## -description


The <code>IPrintOemUni::DisablePDEV</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to delete the private PDEV structure that was allocated by its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> method.


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
</table> 



## -remarks


A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DisablePDEV</code> method.

The <code>IPrintOemUni::DisablePDEV</code> method performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to delete the private PDEV structure that is pointed to by the DEVOBJ structure's <b>pdevOEM</b> member. This PDEV structure is one that was allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> method.


