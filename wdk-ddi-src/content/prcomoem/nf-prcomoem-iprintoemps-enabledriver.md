---
UID: NF:prcomoem.IPrintOemPS.EnableDriver
title: IPrintOemPS::EnableDriver method
author: windows-driver-content
description: The IPrintOemPS::EnableDriver method allows a rendering plug-in for Pscript to hook out some graphics DDI functions.
old-location: print\iprintoemps_enabledriver.htm
old-project: print
ms.assetid: 12e65e91-f540-49fd-a723-c6b93708b166
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemPS::EnableDriver, EnableDriver, print.iprintoemps_enabledriver, print_unidrv-pscript_rendering_2e2fe90b-66ce-4f39-adfa-ebb187700aac.xml, EnableDriver method [Print Devices], prcomoem/IPrintOemPS::EnableDriver, EnableDriver method [Print Devices], IPrintOemPS interface, IPrintOemPS interface [Print Devices], EnableDriver method, IPrintOemPS
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
-	IPrintOemPS.EnableDriver
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPS::EnableDriver method


## -description


The <code>IPrintOemPS::EnableDriver</code> method allows a rendering plug-in for <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> to hook out some graphics DDI functions.


## -syntax


````
STDMETHOD EnableDriver(
   DWORD          DriverVersion,
   DWORD          cbSize,
   PDRVENABLEDATA pded
);
````


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


The <code>IPrintOemPS::EnableDriver</code> method allows a rendering plug-in to perform the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556210">DrvEnableDriver</a> function that is exported by printer graphics DLLs.

Like the <b>DrvEnableDriver</b> function, the <code>IPrintOemPS::EnableDriver</code> method is responsible for providing addresses of internally supported graphics DDI functions, known as hooking functions. It can also perform other one-time initialization operations. Unlike the <b>DrvEnableDriver</b> function, implementation of the <code>IPrintOemPS::EnableDriver</code> method is optional. 
<div class="alert"><b>Note</b>     If you implement <code>IPrintOemPS::EnableDriver</code>, you must also implement <a href="https://msdn.microsoft.com/library/windows/hardware/ff553207">IPrintOemPS::DisableDriver</a>. Actions begun in the former method might need to be completed in the latter method. For example, if a large buffer is allocated in <code>IPrintOemPS::EnableDriver</code>, but not deallocated in <b>IPrintOemPS::DisableDriver</b>, a memory leak can occur.</div><div> </div>The method should fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure and allocate an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556221">DRVFN</a> structures. It should fill the array with pointers to hooking functions, along with winddi.h-defined index values that identify the hooked out graphics DDI functions.

A rendering plug-in for Pscript5 can hook out a graphics DDI function only if the Pscript5 driver defines the function. The following graphics DDI functions are defined in Pscript5 and or Unidrv and can therefore be hooked out:
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556176">DrvAlphaBlend</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556180">DrvBitBlt</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556182">DrvCopyBits</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556202">DrvDitherColor</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556215">DrvEndDoc</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556217">DrvEscape</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556220">DrvFillPath</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556223">DrvFontManagement</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556230">DrvGetGlyphMode</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556236">DrvGradientFill</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556239">DrvIcmCreateColorTransform</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556241">DrvIcmDeleteColorTransform</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556245">DrvLineTo</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556250">DrvNextBand</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556258">DrvPlgBlt</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556260">DrvQueryDeviceSupport</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556259">DrvQueryAdvanceWidths</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556262">DrvQueryFont</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556264">DrvQueryFontData</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556266">DrvQueryFontTree</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556273">DrvRealizeBrush</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556281">DrvSendPage</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556292">DrvStartBanding</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556296">DrvStartDoc</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556298">DrvStartPage</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556302">DrvStretchBlt</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556306">DrvStretchBltROP</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556311">DrvStrokeAndFillPath</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff556316">DrvStrokePath</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff557277">DrvTextOut</a><a href="https://msdn.microsoft.com/library/windows/hardware/ff557283">DrvTransparentBlt</a>If you provide a customized hooking function, it preempts the driver's equivalent graphics DDI function. Hooking functions can also call back into the driver's graphics DDI functions. For more information, see <a href="https://msdn.microsoft.com/33d7d567-5371-4873-a4ef-cd2b06f65d73">Customized Graphics DDI Functions</a>.

Customized hooking functions have the same input and output parameters as the equivalent graphics DDI function, with one exception - where graphics DDI functions receive PDEV pointers, customized hooking functions receive <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> pointers. There are two ways for these functions to receive PDEV pointers:
<ol>
<li>
As the contents of the <b>dhpdev</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure for the destination surface.

For the equivalent customized hooking function, the destination SURFOBJ structure's <b>dhpdev</b> member points to a DEVOBJ structure, and must be cast to type PDEVOBJ when referenced. An example graphics DDI function is <b>DrvBitBlt</b>.

</li>
<li>
As an input argument for a <i>dhpdev</i> parameter.

The equivalent customized hooking function must cast this input parameter to type PDEVOBJ when referencing it. An example graphics DDI function is <b>DrvDitherColor</b>.

</li>
</ol>Note that while a <a href="https://msdn.microsoft.com/58e181ff-c792-41a5-967d-a69a8ff5a041">printer graphics DLL</a> includes the addresses of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556276">DrvResetPDEV</a> functions in the DRVENABLEDATA structure, a rendering plug-in for Pscript5 implements <b>EnablePDEV</b>, <b>DisablePDEV</b>, and <b>ResetPDEV</b> as methods of the <b>IPrintOemPS</b> interface and does not place their addresses in the DRVENABLEDATA structure.

If <code>IPrintOemPS::EnableDriver</code> methods are exported by multiple rendering plug-ins, the methods are called in the order that the plug-ins are specified for installation.
<div class="alert"><b>Note</b>    Each graphics DDI function can be hooked out by one rendering plug-in. If multiple plug-ins attempt to hook out the same graphics DDI function, all hook-outs after the first one are ignored.</div><div> </div>For more information about creating and installing rendering plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.


