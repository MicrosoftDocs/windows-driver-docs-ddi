---
UID: NF:prcomoem.IPrintOemUni.DisablePDEV
title: IPrintOemUni::DisablePDEV method
author: windows-driver-content
description: The IPrintOemUni::DisablePDEV method allows a rendering plug-in for Unidrv to delete the private PDEV structure that was allocated by its IPrintOemUni::EnablePDEV method.
old-location: print\iprintoemuni_disablepdev.htm
old-project: print
ms.assetid: bdceeb23-5d4a-4a1c-98b2-014a4126ca5f
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::DisablePDEV, DisablePDEV
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
req.alt-api: IPrintOemUni.DisablePDEV
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

# IPrintOemUni::DisablePDEV method



## -description
The <code>IPrintOemUni::DisablePDEV</code> method allows a rendering plug-in for <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> to delete the private PDEV structure that was allocated by its <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> method.



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
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed

 


## -remarks
A rendering plug-in for Unidrv must implement the <code>IPrintOemUni::DisablePDEV</code> method.

The <code>IPrintOemUni::DisablePDEV</code> method performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556198">DrvDisablePDEV</a> function that is exported by a printer graphics DLL. Its purpose is to allow a rendering plug-in to delete the private PDEV structure that is pointed to by the DEVOBJ structure's <b>pdevOEM</b> member. This PDEV structure is one that was allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554249">IPrintOemUni::EnablePDEV</a> method.</p>