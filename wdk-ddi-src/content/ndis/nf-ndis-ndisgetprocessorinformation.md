---
UID: NF:ndis.NdisGetProcessorInformation
title: NdisGetProcessorInformation function (ndis.h)
description: The NdisGetProcessorInformation function retrieves information about the CPU topology of the local computer and the set of processors that a miniport driver must use for receive side scaling (RSS).
old-location: netvista\ndisgetprocessorinformation.htm
tech.root: netvista
ms.assetid: 2cee5cf4-7dee-49d2-905c-2b9634137ce4
ms.date: 05/02/2018
ms.keywords: NdisGetProcessorInformation, NdisGetProcessorInformation function [Network Drivers Starting with Windows Vista], ndis/NdisGetProcessorInformation, ndis_sysinfo_ref_1479e4eb-4467-48da-bab6-1f60993f5ef2.xml, netvista.ndisgetprocessorinformation
ms.topic: function
f1_keywords:
 - "ndis/NdisGetProcessorInformation"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, ise       NdisGetProcessorInformationEx or       NdisGetRssProcessorInformation instead.
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisGetProcessorInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGetProcessorInformation function


## -description


The 
  <b>NdisGetProcessorInformation</b> function retrieves information about the CPU topology of the local
  computer and the set of processors that a miniport driver must use for receive side scaling (RSS).


## -parameters




### -param SystemProcessorInfo [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_system_processor_info">
     NDIS_SYSTEM_PROCESSOR_INFO</a> structure that NDIS fills with the information about the CPU topology
     of the system and the RSS processor set.


## -returns



<b>NdisGetProcessorInformation</b> can return one of the following status values:

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The size that was specified in the 
       <b>Header.Size</b> member of the 
       <i>SystemProcessorInfo</i> parameter was too small.

</td>
</tr>
</table>
 




## -remarks



NDIS drivers call the 
    <b>NdisGetProcessorInformation</b> function to retrieve information about the processors on the local
    computer.

RSS-capable miniport drivers that support MSI-X call 
    <b>NdisGetProcessorInformation</b> in their 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">
    MiniportFilterResourceRequirements</a> function. Miniport drivers set the interrupt affinity of the
    allocated MSI-X messages to the RSS processors that are specified in the 
    <b>RssProcessors</b> member of the 
    <i>SystemProcessorInfo</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_system_processor_info">NDIS_SYSTEM_PROCESSOR_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisgetprocessorinformationex">
   NdisGetProcessorInformationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisgetrssprocessorinformation">
   NdisGetRssProcessorInformation</a>
 

 

