---
UID: NF:prcomoem.IPrintCoreUI2.QuerySimulationSupport
title: IPrintCoreUI2::QuerySimulationSupport method
author: windows-driver-content
description: The IPrintCoreUI2::QuerySimulationSupport method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.
old-location: print\iprintcoreui2_querysimulationsupport.htm
old-project: print
ms.assetid: 0136df19-9491-47ea-9a8f-c9a932646686
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreUI2, IPrintCoreUI2::QuerySimulationSupport, QuerySimulationSupport
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
req.alt-api: IPrintCoreUI2.QuerySimulationSupport
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

# IPrintCoreUI2::QuerySimulationSupport method



## -description
The <code>IPrintCoreUI2::QuerySimulationSupport</code> method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.



## -syntax

````
HRESULT QuerySimulationSupport(
  [in]  HANDLE hPrinter,
  [in]  DWORD  dwLevel,
  [out] PBYTE  pCaps,
  [in]  DWORD  cbSize,
  [out] PDWORD pcbNeeded
);
````


## -parameters

### -param hPrinter [in]

Specifies a handle to the printer.


### -param dwLevel [in]

Specifies the spooler simulation capability structure returned in the buffer pointed to by <i>pCaps</i>. Currently, only level 1 of spooler simulation support is provided.

<table>
<tr>
<th>Value</th>
<th>Spooler Simulation Support Structure</th>
</tr>
<tr>
<td>
1

</td>
<td>

<a href="..\printoem\ns-printoem-_simulate_caps_1.md">SIMULATE_CAPS_1</a> (defined in printoem.h)

</td>
</tr>
</table>
 


### -param pCaps [out]

Pointer to the output buffer, which contains a structure of the type indicated by the value in the <i>dwLevel</i> parameter.


### -param cbSize [in]

Specifies the size, in bytes, of the output buffer, which is pointed to by <i>pCaps</i>.


### -param pcbNeeded [out]

Specifies the size, in bytes, of the memory needed to store a structure of the type indicated by <i>dwLevel</i>.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pCaps</i>).

The method was called with <i>pCaps</i> set to <b>NULL</b>.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not supported.

A structure of the type specified by <i>dwLevel</i> is not supported.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The method failed

 


## -remarks
This method is supported only for Windows XP Pscript5 plug-ins, not for Unidrv plug-ins.

The <code>IPrintCoreUI2::QuerySimulationSupport</code> method stores a spooler simulation capability structure in the buffer pointed to by <i>pCaps</i>. This structure specifies the level of spooler support for "N-up" printing, reverse printing, the maximum number of pages that can be printed, collation, and others.


## -see-also
<dl>
<dt>
<a href="..\printoem\ns-printoem-_simulate_caps_1.md">SIMULATE_CAPS_1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::QuerySimulationSupport method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

