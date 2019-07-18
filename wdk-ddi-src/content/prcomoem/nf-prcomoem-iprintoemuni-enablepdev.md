---
UID: NF:prcomoem.IPrintOemUni.EnablePDEV
title: IPrintOemUni::EnablePDEV (prcomoem.h)
description: The IPrintOemUni::EnablePDEV method allows a rendering plug-in for Unidrv to create its own PDEV structure.
old-location: print\iprintoemuni_enablepdev.htm
tech.root: print
ms.assetid: 93028b21-7995-42cd-af14-97e74ae75092
ms.date: 04/20/2018
ms.keywords: EnablePDEV, EnablePDEV method [Print Devices], EnablePDEV method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],EnablePDEV method, IPrintOemUni.EnablePDEV, IPrintOemUni::EnablePDEV, prcomoem/IPrintOemUni::EnablePDEV, print.iprintoemuni_enablepdev, print_unidrv-pscript_rendering_ec7d7a16-5eae-4d4e-8596-7463d967120e.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintOemUni.EnablePDEV"
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
- IPrintOemUni.EnablePDEV
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::EnablePDEV


## -description


The <code>IPrintOemUni::EnablePDEV</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to create its own PDEV structure.


## -parameters




### -param pdevobj

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pPrinterName

Caller-supplied pointer to a text string representing the logical address of the printer.


### -param cPatterns

Caller-supplied value representing the number of HSURF-typed surface handles contained in the buffer pointed to by <i>phsurfPatterns</i>.


### -param phsurfPatterns

Caller-supplied pointer to a buffer that is large enough to contain <i>cPatterns</i> number of HSURF-typed surface handles. The handles represent surface fill patterns.


### -param cjGdiInfo

Caller-supplied value representing the size of the structure pointed to by <i>pGdiInfo</i>.


### -param pGdiInfo

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_gdiinfo">GDIINFO</a> structure.


### -param cjDevInfo

Caller-supplied value representing the size of the structure pointed to by <i>pDevInfo</i>.


### -param pDevInfo

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-tagdevinfo">DEVINFO</a> structure.


### -param pded

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-tagdrvenabledata">DRVENABLEDATA</a> structure containing the addresses of the printer driver's graphics DDI hooking functions. For more information, see the following Remarks section.


### -param pDevOem [out]

Receives a method-supplied pointer to a private PDEV structure. (For more information, see the following Remarks section.)


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
 

If the operation fails, the method should call <b>SetLastError</b> to set an error code.




## -remarks



A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::EnablePDEV</code> method.

The <code>IPrintOemUni::EnablePDEV</code> method performs the same types of operations as the <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to create its own PDEV structure. (For more information about PDEV structures, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-pdev-structures">Customized PDEV Structures</a>.)

If you provide a rendering plug-in that exports the <code>IPrintOemUni::EnablePDEV</code> method, Undrv's printer graphics DLL calls the method from within its <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a> function.

The <code>IPrintOemUni::EnablePDEV</code> method should allocate an instance of its private PDEV structure, initialize it, and return its address as the method's <i>pDevOem</i> parameter. Other plug-in methods receive the address as the <i>pdevOEM</i> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.

The <b>pdevOEM</b> member of the DEVOBJ structure is not used with the <code>IPrintOemUni::EnablePDEV</code> method.

The structures pointed to by the <i>phsurfPatterns</i>, <i>pGdiInfo</i>, and <i>pDevInfo</i> parameter values are the same ones that Unidrv's <b>DrvEnablePDEV</b> function receives. The rendering plug-in can modify the structure contents as necessary. It can supply surface fill patterns by obtaining HSURF-typed surface handles and placing them in the buffer pointed to by <i>phsurfPatterns</i>. Fill pattern types and handle order are listed in the description of <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a>.

The <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-tagdrvenabledata">DRVENABLEDATA</a> structure pointed to by <i>pded</i> contains the addresses of graphics DDI functions provided Unidrv's printer graphics DLL. You are allowed to provide customized hooking functions in your plug-in for these graphics DDI functions. The DRVENABLEDATA structure's contents enable your customized hooking functions to call back to the driver's graphics DDI functions. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-graphics-ddi-functions">Customized Graphics DDI Functions</a>.



