---
UID: NF:prcomoem.IPrintCoreUI2.QuerySimulationSupport
title: IPrintCoreUI2::QuerySimulationSupport (prcomoem.h)
description: The IPrintCoreUI2::QuerySimulationSupport method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.
old-location: print\iprintcoreui2_querysimulationsupport.htm
tech.root: print
ms.assetid: 0136df19-9491-47ea-9a8f-c9a932646686
ms.date: 04/20/2018
ms.keywords: IPrintCoreUI2 interface [Print Devices],QuerySimulationSupport method, IPrintCoreUI2.QuerySimulationSupport, IPrintCoreUI2::QuerySimulationSupport, QuerySimulationSupport, QuerySimulationSupport method [Print Devices], QuerySimulationSupport method [Print Devices],IPrintCoreUI2 interface, prcomoem/IPrintCoreUI2::QuerySimulationSupport, print.iprintcoreui2_querysimulationsupport, print_unidrv-pscript_ui_96f40d94-5dfc-4707-ac4d-0f043a829dd2.xml
ms.topic: method
f1_keywords:
 - "prcomoem/IPrintCoreUI2.QuerySimulationSupport"
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
- prcomoem.h
api_name:
- IPrintCoreUI2.QuerySimulationSupport
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2::QuerySimulationSupport


## -description


The <code>IPrintCoreUI2::QuerySimulationSupport</code> method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_simulate_caps_1">SIMULATE_CAPS_1</a> (defined in printoem.h)

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
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The value in <i>cbSize</i> was smaller than the number of bytes to be written to the output buffer (the buffer pointed to by <i>pCaps</i>).

The method was called with <i>pCaps</i> set to <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not supported.

A structure of the type specified by <i>dwLevel</i> is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The method failed

</td>
</tr>
</table>
 




## -remarks



This method is supported only for Windows XP Pscript5 plug-ins, not for Unidrv plug-ins.

The <code>IPrintCoreUI2::QuerySimulationSupport</code> method stores a spooler simulation capability structure in the buffer pointed to by <i>pCaps</i>. This structure specifies the level of spooler support for "N-up" printing, reverse printing, the maximum number of pages that can be printed, collation, and others.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_simulate_caps_1">SIMULATE_CAPS_1</a>
 

 

