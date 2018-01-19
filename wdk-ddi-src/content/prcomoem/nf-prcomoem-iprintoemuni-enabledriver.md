---
UID: NF:prcomoem.IPrintOemUni.EnableDriver
title: IPrintOemUni::EnableDriver method
author: windows-driver-content
description: The IPrintOemUni::EnableDriver method allows a rendering plug-in for Unidrv to hook out some graphics DDI functions.
old-location: print\iprintoemuni_enabledriver.htm
old-project: print
ms.assetid: 7d7cd1de-569a-4083-8d4c-e073645941e6
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::EnableDriver, EnableDriver
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
req.alt-api: IPrintOemUni.EnableDriver
req.alt-loc: Prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni::EnableDriver method



## -description
The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in for <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> to hook out some graphics DDI functions.



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed

 


## -remarks
A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::EnableDriver</code> method.

The <code>IPrintOemUni::EnableDriver</code> method allows a rendering plug-in to perform the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556210">DrvEnableDriver</a> function that is exported by printer graphics DLLs.

Like the <b>DrvEnableDriver</b> function, the <code>IPrintOemUni::EnableDriver</code> method is responsible for providing addresses of internally supported graphics DDI functions, known as hooking functions. It can also perform other one-time initialization operations. Unlike the <b>DrvEnableDriver</b> function, implementation of <code>IPrintOemUni::EnableDriver</code> is optional.

The method should fill the supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff556206">DRVENABLEDATA</a> structure and allocate an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff556221">DRVFN</a> structures. It should fill the array with pointers to hooking functions, along with winddi.h-defined index values that identify the hooked out graphics DDI functions.

A rendering plug-in for Unidrv can hook out a graphics DDI function only if the Unidrv driver defines the function. The following graphics DDI functions are defined in Unidrv and/or Pscript5 and can therefore be hooked out:

If you provide a customized hooking function, it preempts the driver's equivalent graphics DDI function. Hooking functions can also call back into the driver's graphics DDI functions. For more information see <a href="https://msdn.microsoft.com/33d7d567-5371-4873-a4ef-cd2b06f65d73">Customized Graphics DDI Functions</a>.

Customized hooking functions have the same input and output parameters as the equivalent graphics DDI function, with one exception - where graphics DDI functions receive PDEV pointers, customized hooking functions receive <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> pointers. There are two ways for graphics DDI functions to receive PDEV pointers:

As the contents of the <b>dhpdev</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure for the destination surface.

For the equivalent customized hooking function, the destination SURFOBJ structure's <b>dhpdev</b> member points to a DEVOBJ structure, and must be cast to type PDEVOBJ when referenced. An example graphics DDI function is <b>DrvBitBlt</b>.

As an input argument for a <i>dhpdev</i> parameter.

The equivalent customized hooking function must cast this input parameter to type PDEVOBJ when referencing it. An example graphics DDI function is <b>DrvDitherColor</b>.

Note that while a <a href="https://msdn.microsoft.com/58e181ff-c792-41a5-967d-a69a8ff5a041">printer graphics DLL</a> includes the addresses of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556211">DrvEnablePDEV</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556276">DrvResetPDEV</a> functions in the DRVENABLEDATA structure, a rendering plug-in explicitly exports <b>EnablePDEV</b>, <b>DisablePDEV</b>, and <b>ResetPDEV</b> as methods of the <b>IPrintOemUni</b> interface and does not place their addresses in the DRVENABLEDATA structure.

If <code>IPrintOemUni::EnableDriver</code> methods are exported by multiple rendering plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing rendering plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.</p>