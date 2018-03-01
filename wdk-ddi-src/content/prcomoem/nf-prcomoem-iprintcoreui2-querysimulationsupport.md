---
UID: NF:prcomoem.IPrintCoreUI2.QuerySimulationSupport
title: IPrintCoreUI2::QuerySimulationSupport method
author: windows-driver-content
description: The IPrintCoreUI2::QuerySimulationSupport method retrieves a spooler simulation capability structure, which indicates the kinds of simulation the spooler supports.
old-location: print\iprintcoreui2_querysimulationsupport.htm
old-project: print
ms.assetid: 0136df19-9491-47ea-9a8f-c9a932646686
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintCoreUI2, IPrintCoreUI2 interface [Print Devices], QuerySimulationSupport method, IPrintCoreUI2::QuerySimulationSupport, QuerySimulationSupport method [Print Devices], QuerySimulationSupport method [Print Devices], IPrintCoreUI2 interface, QuerySimulationSupport,IPrintCoreUI2.QuerySimulationSupport, prcomoem/IPrintCoreUI2::QuerySimulationSupport, print.iprintcoreui2_querysimulationsupport, print_unidrv-pscript_ui_96f40d94-5dfc-4707-ac4d-0f043a829dd2.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintCoreUI2.QuerySimulationSupport
product: Windows
targetos: Windows
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

<a href="..\printoem\ns-printoem-_simulate_caps_1.md">SIMULATE_CAPS_1</a>



<a href="..\prcomoem\nn-prcomoem-iprintcoreui2.md">IPrintCoreUI2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::QuerySimulationSupport method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

