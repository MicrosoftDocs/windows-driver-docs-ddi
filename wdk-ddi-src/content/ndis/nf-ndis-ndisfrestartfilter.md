---
UID: NF:ndis.NdisFRestartFilter
title: NdisFRestartFilter function
author: windows-driver-content
description: A filter driver calls the NdisFRestartFilter function to request NDIS to initiate a restart operation for a filter module.
old-location: netvista\ndisfrestartfilter.htm
tech.root: netvista
ms.assetid: 8b0fc032-3ec0-4e18-a5f5-6409db8ae42d
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisFRestartFilter, NdisFRestartFilter function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_c95250d0-3081-40cc-a39f-0d5c1ce51925.xml, ndis/NdisFRestartFilter, netvista.ndisfrestartfilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFRestartFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFRestartFilter function


## -description


A filter driver calls the
  <b>NdisFRestartFilter</b> function to request NDIS to initiate a restart operation for a filter
  module.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


## -returns



<b>NdisFRestartFilter</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562611">NdisFRestartFilter</a> returns NDIS_STATUS_SUCCESS if it started the restart operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562611">NdisFRestartFilter</a> failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562611">NdisFRestartFilter</a> returns NDIS_STATUS_FAILURE if none of the preceding values applies.

</td>
</tr>
</table>
 




## -remarks



The filter driver can change the filter module attributes at run time by calling the 
    <b>NdisFRestartFilter</b> function. 
    <b>NdisFRestartFilter</b> schedules a pause and then a restart operation for the specified filter
    module.

Before NDIS restarts the filter module, it calls the 
    <a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a> function for the filter module. From 
    its <i>FilterSetModuleOptions</i> function, the filter driver can change the data handlers for that filter module by
    calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a> function
    and specifying a new set of handlers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/04b7ac32-8996-4648-8c88-aa9f630b1bc4">FilterSetModuleOptions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564550">NdisSetOptionalHandlers</a>
 

 

