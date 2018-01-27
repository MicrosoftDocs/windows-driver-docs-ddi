---
UID: NF:prcomoem.IPrintOemPS.ResetPDEV
title: IPrintOemPS::ResetPDEV method
author: windows-driver-content
description: The IPrintOemPS::ResetPDEV method allows a rendering plug-in for Pscript5 to reset its PDEV structure.
old-location: print\iprintoemps_resetpdev.htm
old-project: print
ms.assetid: 10248026-471a-4419-9c96-3502c24a6e96
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_unidrv-pscript_rendering_d7b128bc-174c-4d06-8ffa-8df31ac22303.xml, IPrintOemPS::ResetPDEV, prcomoem/IPrintOemPS::ResetPDEV, print.iprintoemps_resetpdev, ResetPDEV method [Print Devices], IPrintOemPS interface, IPrintOemPS interface [Print Devices], ResetPDEV method, ResetPDEV, ResetPDEV method [Print Devices], IPrintOemPS
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
-	IPrintOemPS.ResetPDEV
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS::ResetPDEV method


## -description


The <code>IPrintOemPS::ResetPDEV</code> method allows a rendering plug-in for Pscript5 to reset its PDEV structure.


## -syntax


````
STDMETHOD ResetPDEV(
   PDEVOBJ pdevobjOld,
   PDEVOBJ pdevobjNew
);
````


## -parameters




### -param pdevobjOld

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure containing current PDEV information.


### -param pdevobjNew

Caller-supplied pointer to a DEVOBJ structure into which the method should place new PDEV information.


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

If the operation fails it should call <b>SetLastError</b>.



## -remarks


A rendering plug-in's <code>IPrintOemPS::ResetPDEV</code> method performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556276">DrvResetPDEV</a> function that is exported by a printer graphics DLL. During the processing of an application's call to the Microsoft Windows SDK <b>ResetDC</b> function, the <code>IPrintOemPS::ResetPDEV</code> method is called by the <b>DrvResetPDEV</b> function in Pscript5's printer graphics DLL. For more information about when <b>DrvResetPDEV</b> is called, see its description.

The rendering plug-in's private PDEV structure's address is contained in the <b>pdevOEM</b> member of the DEVOBJ structure pointed to by <i>pdevobjOld</i>. The <code>IPrintOemPS::ResetPDEV</code> method should use relevant members of this old structure to fill in the new structure, which is referenced through <i>pdevobjNew</i>.


