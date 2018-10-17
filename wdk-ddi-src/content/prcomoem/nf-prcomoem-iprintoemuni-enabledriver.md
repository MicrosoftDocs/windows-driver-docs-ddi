---
UID: NF:prcomoem.IPrintOemUni.EnableDriver
title: IPrintOemUni::EnableDriver
author: windows-driver-content
description: The IPrintOemUni::EnableDriver method allows a rendering plug-in for Unidrv to hook out some graphics DDI functions.
old-location: print\iprintoemuni_enabledriver.htm
tech.root: print
ms.assetid: 7d7cd1de-569a-4083-8d4c-e073645941e6
ms.date: 4/20/2018
ms.keywords: EnableDriver, EnableDriver method [Print Devices], EnableDriver method [Print Devices],IPrintOemUni interface, IPrintOemUni interface [Print Devices],EnableDriver method, IPrintOemUni.EnableDriver, IPrintOemUni::EnableDriver, prcomoem/IPrintOemUni::EnableDriver, print.iprintoemuni_enabledriver, print_unidrv-pscript_rendering_804d9469-6ac6-4220-b123-25a2d226b609.xml
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintOemUni.EnableDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni::EnableDriver


## -description


The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> to hook out some graphics DDI functions.


## -parameters




### -param DriverVersion

Caller-supplied interface version number. This value is defined by PRINTER_OEMINTF_VERSION, in printoem.h.


### -param cbSize

Caller-supplied size, in bytes, of the structure pointed to by <i>pded</i>.


### -param pded

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure.


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

The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in to perform the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556210">DrvEnableDriver</a> function that is exported by printer graphics DLLs.

Like the <b>DrvEnableDriver</b> function, the <code>IPrintOemUni::EnableDriver</code> method is responsible for providing addresses of internally supported graphics DDI functions, known as hooking functions. It can also perform other one-time initialization operations. Unlike the <b>DrvEnableDriver</b> function, implementation of <code>IPrintOemUni::EnableDriver</code> is optional.

<div class="alert"><b>Note</b>     If you implement <code>IPrintOemUni::EnableDriver</code>, you must also implement <a href="https://msdn.microsoft.com/library/windows/hardware/ff554232">IPrintOemUni::DisableDriver</a>. Actions begun in the former method might need to be completed in the latter method. For example, if a large buffer is allocated in <code>IPrintOemUni::EnableDriver</code>, but not deallocated in <b>IPrintOemUni::DisableDriver</b>, a memory leak can occur.</div>
<div> </div>
The method should fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure and allocate an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556221">DRVFN</a> structures. It should fill the array with pointers to hooking functions, along with winddi.h-defined index values that identify the hooked out graphics DDI functions.

A rendering plug-in for Unidrv can hook out a graphics DDI function only if the Unidrv driver defines the function. The following graphics DDI functions are defined in Unidrv and/or Pscript5 and can therefore be hooked out:

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556176">DrvAlphaBlend</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556180">DrvBitBlt</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556182">DrvCopyBits</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556202">DrvDitherColor</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556215">DrvEndDoc</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556217">DrvEscape</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556220">DrvFillPath</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556223">DrvFontManagement</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556230">DrvGetGlyphMode</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556236">DrvGradientFill</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556239">DrvIcmCreateColorTransform</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556241">DrvIcmDeleteColorTransform</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556245">DrvLineTo</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556250">DrvNextBand</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556258">DrvPlgBlt</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556259">DrvQueryAdvanceWidths</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556260">DrvQueryDeviceSupport</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556262">DrvQueryFont</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556264">DrvQueryFontData</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556266">DrvQueryFontTree</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556273">DrvRealizeBrush</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556281">DrvSendPage</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556292">DrvStartBanding</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556296">DrvStartDoc</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556298">DrvStartPage</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556302">DrvStretchBlt</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556306">DrvStretchBltROP</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556311">DrvStrokeAndFillPath</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556316">DrvStrokePath</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557277">DrvTextOut</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557283">DrvTransparentBlt</a>
If you provide a customized hooking function, it preempts the driver's equivalent graphics DDI function. Hooking functions can also call back into the driver's graphics DDI functions. For more information see <a href="https://msdn.microsoft.com/33d7d567-5371-4873-a4ef-cd2b06f65d73">Customized Graphics DDI Functions</a>.

Customized hooking functions have the same input and output parameters as the equivalent graphics DDI function, with one exception - where graphics DDI functions receive PDEV pointers, customized hooking functions receive <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> pointers. There are two ways for graphics DDI functions to receive PDEV pointers:

<ul>
<li>
As the contents of the <b>dhpdev</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure for the destination surface.

For the equivalent customized hooking function, the destination SURFOBJ structure's <b>dhpdev</b> member points to a DEVOBJ structure, and must be cast to type PDEVOBJ when referenced. An example graphics DDI function is <b>DrvBitBlt</b>.

</li>
<li>
As an input argument for a <i>dhpdev</i> parameter.

The equivalent customized hooking function must cast this input parameter to type PDEVOBJ when referencing it. An example graphics DDI function is <b>DrvDitherColor</b>.

</li>
</ul>
Note that while a <a href="https://msdn.microsoft.com/58e181ff-c792-41a5-967d-a69a8ff5a041">printer graphics DLL</a> includes the addresses of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556276">DrvResetPDEV</a> functions in the DRVENABLEDATA structure, a rendering plug-in explicitly exports <b>EnablePDEV</b>, <b>DisablePDEV</b>, and <b>ResetPDEV</b> as methods of the <b>IPrintOemUni</b> interface and does not place their addresses in the DRVENABLEDATA structure.

If <code>IPrintOemUni::EnableDriver</code> methods are exported by multiple rendering plug-ins, the methods are called in the order that the plug-ins are specified for installation.

<div class="alert"><b>Note</b>    Each graphics DDI function can be hooked out by only one rendering plug-in. If multiple plug-ins attempt to hook out the same graphics DDI function, all hook-outs after the first one are ignored.</div>
<div> </div>
For more information about creating and installing rendering plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.



