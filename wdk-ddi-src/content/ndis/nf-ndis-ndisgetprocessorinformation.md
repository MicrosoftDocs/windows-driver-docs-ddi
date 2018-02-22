---
UID: NF:ndis.NdisGetProcessorInformation
title: NdisGetProcessorInformation function
author: windows-driver-content
description: The NdisGetProcessorInformation function retrieves information about the CPU topology of the local computer and the set of processors that a miniport driver must use for receive side scaling (RSS).
old-location: netvista\ndisgetprocessorinformation.htm
old-project: netvista
ms.assetid: 2cee5cf4-7dee-49d2-905c-2b9634137ce4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisGetProcessorInformation function [Network Drivers Starting with Windows Vista], netvista.ndisgetprocessorinformation, NdisGetProcessorInformation, ndis/NdisGetProcessorInformation, ndis_sysinfo_ref_1479e4eb-4467-48da-bab6-1f60993f5ef2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGetProcessorInformation
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisGetProcessorInformation function


## -description


The 
  <b>NdisGetProcessorInformation</b> function retrieves information about the CPU topology of the local
  computer and the set of processors that a miniport driver must use for receive side scaling (RSS).


## -syntax


````
NDIS_STATUS NdisGetProcessorInformation(
  _Inout_ PNDIS_SYSTEM_PROCESSOR_INFO SystemProcessorInfo
);
````


## -parameters




### -param SystemProcessorInfo [in, out]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff559452(d=robot)">
    MiniportFilterResourceRequirements</a> function. Miniport drivers set the interrupt affinity of the
    allocated MSI-X messages to the RSS processors that are specified in the 
    <b>RssProcessors</b> member of the 
    <i>SystemProcessorInfo</i> parameter.




## -see-also

<a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
   NdisGetProcessorInformationEx</a>



<a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
   NdisGetProcessorInformationEx</a>



<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>



<a href="..\ndis\nf-ndis-ndisgetrssprocessorinformation.md">
   NdisGetRssProcessorInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetProcessorInformation function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

