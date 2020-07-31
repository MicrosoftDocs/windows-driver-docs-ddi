---
UID: NS:ntddndis._NDIS_RSS_PROCESSOR_INFO
title: _NDIS_RSS_PROCESSOR_INFO (ntddndis.h)
description: The NDIS_RSS_PROCESSOR_INFO structure specifies information about the CPU receive side scaling (RSS) processor set on the local computer.
old-location: netvista\ndis_rss_processor_info.htm
tech.root: netvista
ms.assetid: 7f40a815-0247-428c-a46f-d3cdbf7e8058
ms.date: 05/02/2018
keywords: ["_NDIS_RSS_PROCESSOR_INFO structure"]
ms.keywords: "*PNDIS_RSS_PROCESSOR_INFO, NDIS_RSS_PROCESSOR_INFO, NDIS_RSS_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_RSS_PROCESSOR_INFO, PNDIS_RSS_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSS_PROCESSOR_INFO, ndis_processor_group_ref_de5d0ed6-e4b3-4074-8816-8ab3c3ff0c4d.xml, netvista.ndis_rss_processor_info, ntddndis/NDIS_RSS_PROCESSOR_INFO, ntddndis/PNDIS_RSS_PROCESSOR_INFO"
f1_keywords:
 - "ntddndis/NDIS_RSS_PROCESSOR_INFO"
 - "NDIS_RSS_PROCESSOR_INFO"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_RSS_PROCESSOR_INFO
targetos: Windows
req.typenames: NDIS_RSS_PROCESSOR_INFO, *PNDIS_RSS_PROCESSOR_INFO
---

# _NDIS_RSS_PROCESSOR_INFO structure


## -description


The <b>NDIS_RSS_PROCESSOR_INFO</b> structure specifies information about the CPU receive side scaling (RSS)
  processor set on the local computer.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RSS_PROCESSOR_INFO</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RSS_PROCESSOR_INFO</b>. NDIS also sets the 
     <b>Revision</b> and 
     <b>Size</b> members to the values shown in the following table.

<table>
<tr>
<th>NDIS version</th>
<th>Revision value</th>
<th>Size value</th>
</tr>
<tr>
<td>
NDIS 6.20
       

</td>
<td><b>NDIS_RSS_PROCESSOR_INFO_REVISION_1</b></td>
<td><b>NDIS_SIZEOF_RSS_PROCESSOR_INFO_REVISION_1</b></td>
</tr>
<tr>
<td>
NDIS 6.30
       

</td>
<td><b>NDIS_RSS_PROCESSOR_INFO_REVISION_2</b></td>
<td><b>NDIS_SIZEOF_RSS_PROCESSOR_INFO_REVISION_2</b></td>
</tr>
</table>
 


### -field Flags

Reserved. NDIS sets this member to zero.


### -field RssBaseProcessor

The starting processor number that is used for RSS. 

<div class="alert"><b>Note</b>  The RSS base CPU number is the CPU number of the first CPU that RSS can use. RSS cannot use the CPUs that are numbered below the base CPU number.</div>
<div> </div>

### -field MaxNumRssProcessors

The maximum number of processors that are used for RSS


### -field PreferredNumaNode

The preferred NUMA node, which is the node closest to the NIC


### -field RssProcessorArrayOffset

The offset, in bytes, from the start of the structure to an array of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a> structures, with each
     entry describing an RSS processor on the system. The 
     <b>RssProcessorCount</b> member contains the number of <b>NDIS_RSS_PROCESSOR</b> structures in the array. The 
     <b>RssProcessorEntrySize</b> member contains the size of the <b>NDIS_RSS_PROCESSOR</b> structures in the
     array.


### -field RssProcessorCount

The number of elements in the array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a> structures that follows this
     structure.


### -field RssProcessorEntrySize

The size, in bytes, of elements in the array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a> structures that follows this
     structure.


### -field RssMaxProcessor

The maximum processor number that is used for RSS.


### -field RssProfile

Reserved.


## -remarks



NDIS network drivers use the <b>NDIS_RSS_PROCESSOR_INFO</b> structure in calls to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetrssprocessorinformation">
    NdisGetRssProcessorInformation</a> function. After 
    <b>NdisGetRssProcessorInformation</b> returns, this structure contains information about the set of
    processors that will be used for receive side scaling (RSS).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/jj849980(v=vs.85)">NDIS_RSS_PROFILE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetrssprocessorinformation">
   NdisGetRssProcessorInformation</a>
 

 

