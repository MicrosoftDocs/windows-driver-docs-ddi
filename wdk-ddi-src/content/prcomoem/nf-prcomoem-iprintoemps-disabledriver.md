---
UID: NF:prcomoem.IPrintOemPS.DisableDriver
title: IPrintOemPS::DisableDriver method
author: windows-driver-content
description: The IPrintOemPS::DisableDriver method allows a rendering plug-in for Pscript to free resources that were allocated by the plug-in's IPrintOemPS::EnableDriver method.
old-location: print\iprintoemps_disabledriver.htm
old-project: print
ms.assetid: 4fa25706-dc79-45fd-a805-7b9d110213ed
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemPS, IPrintOemPS::DisableDriver, DisableDriver
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
req.alt-api: IPrintOemPS.DisableDriver
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

# IPrintOemPS::DisableDriver method



## -description
The <code>IPrintOemPS::DisableDriver</code> method allows a rendering plug-in for <a href="wdkgloss.p#wdkgloss.pscript#wdkgloss.pscript"><i>Pscript</i></a> to free resources that were allocated by the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a> method.



## -syntax

````
STDMETHOD DisableDriver();
````


## -parameters


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 

The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 

The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
The <code>IPrintOemPS::DisableDriver</code> method, provided by rendering plug-ins for Pscript5, performs the same types of operations as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556196">DrvDisableDriver</a> function that is exported by Pscript5's printer graphics DLL.

<code>IPrintOemPS::DisableDriver</code> and <b>IPrintOemPS::EnableDriver</b> must be implemented as a pair. If you implement one, you must implement the other. For more information, see the Remarks section in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553212">IPrintOemPS::EnableDriver</a>. 

This is the last <b>IPrintOemPS</b> interface method that is called before the rendering plug-in is unloaded.</p>