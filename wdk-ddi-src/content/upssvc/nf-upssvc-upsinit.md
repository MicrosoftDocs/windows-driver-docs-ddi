---
UID: NF:upssvc.UPSInit
title: UPSInit function
author: windows-driver-content
description: The UPSInit function initializes a UPS minidriver, opens communication to the UPS unit, updates the registry, and causes the minidriver to start monitoring the UPS unit.
old-location: battery\upsinit.htm
tech.root: battery
ms.assetid: abcb1f9c-3de3-430c-87e0-6648d60ca420
ms.date: 02/15/2018
ms.keywords: UPSInit, UPSInit function [Battery Devices], UPS_fns_855934b9-5f74-4308-9bed-5fd85d039247.xml, battery.upsinit, upssvc/UPSInit
ms.topic: function
req.header: upssvc.h
req.include-header: Upssvc.h
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
-	HeaderDef
api_location:
-	Upssvc.h
api_name:
-	UPSInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# UPSInit function


## -description


The <b>UPSInit</b> function initializes a UPS minidriver, opens communication to the UPS unit, updates the registry, and causes the minidriver to start monitoring the UPS unit.


## -parameters








## -returns



The <b>UPSInit</b> function returns one of the following DWORD values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_INITOK</b></dt>
</dl>
</td>
<td width="60%">
No errors were encountered during initialization. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_INITREGISTRYERROR</b></dt>
</dl>
</td>
<td width="60%">
An error occurred while accessing the registry.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_INITCOMMOPENERROR</b></dt>
</dl>
</td>
<td width="60%">
An error occurred while opening the COM port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_INITCOMMSETUPERROR</b></dt>
</dl>
</td>
<td width="60%">
An error occurred while setting up the COM port.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>UPS_INITUNKNOWNERROR</b></dt>
</dl>
</td>
<td width="60%">
An unidentified error occurred.

</td>
</tr>
</table>
 




## -remarks



The <b>UPSInit</b> function is the first function exported by a UPS minidriver that is called by the UPS service. The function must complete all initialization operations for the minidriver, including the following:

<ul>
<li>
Opening a communication path to the UPS unit

</li>
<li>
Determining the initial state of the UPS unit

</li>
<li>
Updating <a href="https://msdn.microsoft.com/d0d4ef8f-9df1-48a3-b0fc-cea4eb3cdf40">UPS registry entries</a>


</li>
<li>
Beginning the monitoring of the UPS unit

</li>
</ul>
If the <b>UPSInit</b> function returns a value other than UPS_INITOK, the UPS service immediately calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536314">UPSStop</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536314">UPSStop</a>
 

 

