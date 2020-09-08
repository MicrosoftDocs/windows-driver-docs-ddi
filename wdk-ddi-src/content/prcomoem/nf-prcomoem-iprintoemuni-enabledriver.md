---
UID: NF:prcomoem.IPrintOemUni.EnableDriver
title: IPrintOemUni::EnableDriver (prcomoem.h)
description: The IPrintOemUni::EnableDriver method allows a rendering plug-in for Unidrv to hook out some graphics DDI functions.
old-location: print\iprintoemuni_enabledriver.htm
tech.root: print
ms.assetid: 7d7cd1de-569a-4083-8d4c-e073645941e6
ms.date: 04/20/2018
keywords: ["IPrintOemUni::EnableDriver"]
ms.keywords: EnableDriver, EnableDriver method [Print Devices], EnableDriver method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],EnableDriver method, IPrintOemUni.EnableDriver, IPrintOemUni::EnableDriver, prcomoem/IPrintOemUni::EnableDriver, print.iprintoemuni_enabledriver, print_unidrv-pscript_rendering_804d9469-6ac6-4220-b123-25a2d226b609.xml
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
 - IPrintOemUni::EnableDriver
 - prcomoem/IPrintOemUni::EnableDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemUni.EnableDriver
---

# IPrintOemUni::EnableDriver


## -description

The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in for <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> to hook out some graphics DDI functions.

## -parameters

### -param DriverVersion

Caller-supplied interface version number. This value is defined by PRINTER_OEMINTF_VERSION, in printoem.h.

### -param cbSize

Caller-supplied size, in bytes, of the structure pointed to by <i>pded</i>.

### -param pded

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-tagdrvenabledata">DRVENABLEDATA</a> structure.

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

A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::EnableDriver</code> method.

The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in to perform the same types of operations as the <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenabledriver">DrvEnableDriver</a> function that is exported by printer graphics DLLs.

Like the <b>DrvEnableDriver</b> function, the <code>IPrintOemUni::EnableDriver</code> method is responsible for providing addresses of internally supported graphics DDI functions, known as hooking functions. It can also perform other one-time initialization operations. Unlike the <b>DrvEnableDriver</b> function, implementation of <code>IPrintOemUni::EnableDriver</code> is optional.

<div class="alert"><b>Note</b>     If you implement <code>IPrintOemUni::EnableDriver</code>, you must also implement <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-disabledriver">IPrintOemUni::DisableDriver</a>. Actions begun in the former method might need to be completed in the latter method. For example, if a large buffer is allocated in <code>IPrintOemUni::EnableDriver</code>, but not deallocated in <b>IPrintOemUni::DisableDriver</b>, a memory leak can occur.</div>
<div> </div>
The method should fill the supplied <a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-tagdrvenabledata">DRVENABLEDATA</a> structure and allocate an array of <a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-_drvfn">DRVFN</a> structures. It should fill the array with pointers to hooking functions, along with winddi.h-defined index values that identify the hooked out graphics DDI functions.

A rendering plug-in for Unidrv can hook out a graphics DDI function only if the Unidrv driver defines the function. The following graphics DDI functions are defined in Unidrv and/or Pscript5 and can therefore be hooked out:

<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvalphablend">DrvAlphaBlend</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvbitblt">DrvBitBlt</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvcopybits">DrvCopyBits</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvdithercolor">DrvDitherColor</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenddoc">DrvEndDoc</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvescape">DrvEscape</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvfillpath">DrvFillPath</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvfontmanagement">DrvFontManagement</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvgetglyphmode">DrvGetGlyphMode</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvgradientfill">DrvGradientFill</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvicmcreatecolortransform">DrvIcmCreateColorTransform</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvicmdeletecolortransform">DrvIcmDeleteColorTransform</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvlineto">DrvLineTo</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvnextband">DrvNextBand</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvplgblt">DrvPlgBlt</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvqueryadvancewidths">DrvQueryAdvanceWidths</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvquerydevicesupport">DrvQueryDeviceSupport</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvqueryfont">DrvQueryFont</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvqueryfontdata">DrvQueryFontData</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvqueryfonttree">DrvQueryFontTree</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvrealizebrush">DrvRealizeBrush</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvsendpage">DrvSendPage</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstartbanding">DrvStartBanding</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstartdoc">DrvStartDoc</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstartpage">DrvStartPage</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstretchblt">DrvStretchBlt</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstretchbltrop">DrvStretchBltROP</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstrokeandfillpath">DrvStrokeAndFillPath</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvstrokepath">DrvStrokePath</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvtextout">DrvTextOut</a>
<a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvtransparentblt">DrvTransparentBlt</a>
If you provide a customized hooking function, it preempts the driver's equivalent graphics DDI function. Hooking functions can also call back into the driver's graphics DDI functions. For more information see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customized-graphics-ddi-functions">Customized Graphics DDI Functions</a>.

Customized hooking functions have the same input and output parameters as the equivalent graphics DDI function, with one exception - where graphics DDI functions receive PDEV pointers, customized hooking functions receive <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_devobj">DEVOBJ</a> pointers. There are two ways for graphics DDI functions to receive PDEV pointers:

<ul>
<li>
As the contents of the <b>dhpdev</b> member of a <a href="https://docs.microsoft.com/windows/win32/api/winddi/ns-winddi-_surfobj">SURFOBJ</a> structure for the destination surface.

For the equivalent customized hooking function, the destination SURFOBJ structure's <b>dhpdev</b> member points to a DEVOBJ structure, and must be cast to type PDEVOBJ when referenced. An example graphics DDI function is <b>DrvBitBlt</b>.

</li>
<li>
As an input argument for a <i>dhpdev</i> parameter.

The equivalent customized hooking function must cast this input parameter to type PDEVOBJ when referencing it. An example graphics DDI function is <b>DrvDitherColor</b>.

</li>
</ul>
Note that while a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/printer-graphics-dll">printer graphics DLL</a> includes the addresses of its <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a>, <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvdisablepdev">DrvDisablePDEV</a>, and <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvresetpdev">DrvResetPDEV</a> functions in the DRVENABLEDATA structure, a rendering plug-in explicitly exports <b>EnablePDEV</b>, <b>DisablePDEV</b>, and <b>ResetPDEV</b> as methods of the <b>IPrintOemUni</b> interface and does not place their addresses in the DRVENABLEDATA structure.

If <code>IPrintOemUni::EnableDriver</code> methods are exported by multiple rendering plug-ins, the methods are called in the order that the plug-ins are specified for installation.

<div class="alert"><b>Note</b>    Each graphics DDI function can be hooked out by only one rendering plug-in. If multiple plug-ins attempt to hook out the same graphics DDI function, all hook-outs after the first one are ignored.</div>
<div> </div>
For more information about creating and installing rendering plug-ins, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/customizing-microsoft-s-printer-drivers">Customizing Microsoft's Printer Drivers</a>.

