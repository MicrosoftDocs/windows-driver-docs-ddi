---
UID: NF:prcomoem.IPrintOemDriverPS.DrvGetDriverSetting
title: IPrintOemDriverPS::DrvGetDriverSetting method
author: windows-driver-content
description: The IPrintOemDriverPS::DrvGetDriverSetting method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintoemdriverps_drvgetdriversetting.htm
old-project: print
ms.assetid: c3e9775b-a5ab-42e4-a889-a746a7243b37
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemDriverPS, IPrintOemDriverPS::DrvGetDriverSetting, DrvGetDriverSetting
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
req.alt-api: IPrintOemDriverPS.DrvGetDriverSetting
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

# IPrintOemDriverPS::DrvGetDriverSetting method



## -description
The <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is provided by the Pscript5 driver so that rendering plug-ins can obtain the current status of printer features and other internal information.



## -syntax

````
HRESULT DrvGetDriverSetting(
   PVOID  pdriverobj,
   PCSTR  Feature,
   PVOID  pOutput,
   DWORD  cbSize,
   PDWORD pcbNeeded,
   PDWORD pdwOptionsReturned
);
````


## -parameters

### -param pdriverobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param Feature 

Caller supplied value identifying the printer feature for which option settings will be returned. This can be either a string pointer or a constant, as described in the following Remarks section.


### -param pOutput 

Caller-supplied pointer to a buffer to receive the specified information.


### -param cbSize 

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutput</i>.


### -param pcbNeeded 

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


### -param pdwOptionsReturned 

Caller-supplied pointer to a location to receive the number of option strings placed in <i>pOutput</i>.


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

 


## -remarks
When the <code>IPrintOemDriverPS::DrvGetDriverSetting</code> method is called, either a string pointer or a constant value can be specified for <i>pFeatureKeyword</i>.

If <i>pFeatureKeyword</i> is a string, it must represent a keyword argument to an *<b>OpenUI</b> entry in a Pscript5 minidriver's PPD file.

The method should return one or more NULL-terminated strings in the buffer pointed to by <i>pOutput</i>. Each string should represent the name of a currently selected option. The number of strings should be returned in <i>pdwOptionsReturned</i>.

If <i>pFeatureKeyword</i> is a constant, it must be one of the <b>OEMGDS_</b>-prefixed constants defined in printoem.h. The method should return the value indicated by the specified constant by placing it in the buffer pointed to by <i>pOutput</i>. The value returned in <i>pdwOptionsReturned</i> must be 1.</p>