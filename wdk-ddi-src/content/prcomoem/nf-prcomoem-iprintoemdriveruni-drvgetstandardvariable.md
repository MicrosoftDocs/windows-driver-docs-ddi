---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetStandardVariable
title: IPrintOemDriverUni::DrvGetStandardVariable method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvGetStandardVariable method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's standard variables.
old-location: print\iprintoemdriveruni_drvgetstandardvariable.htm
old-project: print
ms.assetid: d55d3130-14e7-438f-bfb5-18927466bd60
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni::DrvGetStandardVariable, DrvGetStandardVariable
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
req.alt-api: IPrintOemDriverUni.DrvGetStandardVariable
req.alt-loc: prcomoem.h
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

# IPrintOemDriverUni::DrvGetStandardVariable method



## -description
The <code>IPrintOemDriverUni::DrvGetStandardVariable</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>.



## -syntax

````
HRESULT DrvGetStandardVariable(
   PDEVOBJ pdevobj,
   DWORD   dwIndex,
   PVOID   pBuffer,
   DWORD   cbSize,
   PDWORD  pcbNeeded
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwIndex 

Caller-supplied, SVI_-prefixed index into the list of Unidrv's standard variables. The SVI_-prefixed index values are defined in printoem.h.


### -param pBuffer 

Caller-supplied pointer to a DWORD to receive the standard variable's current value.


### -param cbSize 

Caller-supplied size of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded 

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
