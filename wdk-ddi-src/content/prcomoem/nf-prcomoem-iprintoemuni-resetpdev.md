---
UID: NF:prcomoem.IPrintOemUni.ResetPDEV
title: IPrintOemUni::ResetPDEV (prcomoem.h)
description: The IPrintOemUni::ResetPDEV method allows a rendering plug-in for Unidrv to reset its PDEV structure.
old-location: print\iprintoemuni_resetpdev.htm
tech.root: print
ms.assetid: 7398a265-56e0-4b40-bfbb-0d72e7309efc
ms.date: 04/20/2018
keywords: ["IPrintOemUni::ResetPDEV"]
ms.keywords: IPrintOemUni interface [Print Devices],ResetPDEV method, IPrintOemUni.ResetPDEV, IPrintOemUni::ResetPDEV, ResetPDEV, ResetPDEV method [Print Devices], ResetPDEV method [Print Devices],IPrintOemUni interface, prcomoem/IPrintOemUni::ResetPDEV, print.iprintoemuni_resetpdev, print_unidrv-pscript_rendering_7b938048-0e07-4e06-8f74-ed13f188d210.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemUni::ResetPDEV
 - prcomoem/IPrintOemUni::ResetPDEV
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemUni.ResetPDEV
---

# IPrintOemUni::ResetPDEV


## -description

The <code>IPrintOemUni::ResetPDEV</code> method allows a rendering plug-in for Unidrv to reset its PDEV structure.

## -parameters

### -param pdevobjOld

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> structure containing current PDEV information.

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
The operation failed.

</td>
</tr>
</table>
 

If the operation fails, this method should call <b>SetLastError</b>.

## -remarks

A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::ResetPDEV</code> method.

A rendering plug-in's <code>IPrintOemUni::ResetPDEV</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvresetpdev">DrvResetPDEV</a> function that is exported by a printer graphics DLL. During the processing of an application's call to the Microsoft Windows SDK <b>ResetDC</b> function, the <code>IPrintOemUni::ResetPDEV</code> method is called by the <b>DrvResetPDEV</b> function in Unidrv's printer graphics DLL. For more information about when <b>DrvResetPDEV</b> is called, see its description.

The rendering plug-in's private PDEV structure's address is contained in the <b>pdevOEM</b> member of the DEVOBJ structure pointed to by <i>pdevobjOld</i>. The <code>IPrintOemUni::ResetPDEV</code> method should use relevant members of this old structure to fill in the new structure, which is referenced through <i>pdevobjNew</i>.

## -see-also

<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvresetpdev">DrvResetPDEV</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemuni">IPrintOemUni</a>

