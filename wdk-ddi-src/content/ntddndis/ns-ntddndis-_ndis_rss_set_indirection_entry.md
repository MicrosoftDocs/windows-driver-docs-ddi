---
UID: NS:ntddndis._NDIS_RSS_SET_INDIRECTION_ENTRY
title: "_NDIS_RSS_SET_INDIRECTION_ENTRY"
author: windows-driver-content
description: The NDIS_RSS_SET_INDIRECTION_ENTRY structure represents a command to set a single indirection table entry.
old-location: netvista\ndis_rss_set_indirection_entry.htm
old-project: netvista
ms.assetid: 4430E19F-C603-4C52-8FC8-C36197FD2996
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_RSS_SET_INDIRECTION_ENTRY, NDIS_RSS_SET_INDIRECTION_ENTRY, NDIS_RSS_SET_INDIRECTION_ENTRY structure [Network Drivers Starting with Windows Vista], NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR, NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR, PNDIS_RSS_SET_INDIRECTION_ENTRY, PNDIS_RSS_SET_INDIRECTION_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSS_SET_INDIRECTION_ENTRY, netvista.ndis_rss_set_indirection_entry, ntddndis/NDIS_RSS_SET_INDIRECTION_ENTRY, ntddndis/PNDIS_RSS_SET_INDIRECTION_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.80 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RSS_SET_INDIRECTION_ENTRY
product: Windows
targetos: Windows
req.typenames: NDIS_RSS_SET_INDIRECTION_ENTRY, *PNDIS_RSS_SET_INDIRECTION_ENTRY
---

# _NDIS_RSS_SET_INDIRECTION_ENTRY structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
<div class="alert"><b>Warning</b>  RSSv2 is preview only in Windows 10, version 1709.</div><div> </div>The <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> structure represents a command to set a single indirection table entry. It is contained in an <a href="https://msdn.microsoft.com/9AB69EC6-FE78-4242-89C7-D36AA16676BF">NDIS_RSS_SET_INDIRECTION_ENTRIES</a> structure, which is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a> OID. OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES is a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID</a> for <a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>.


## -struct-fields




### -field SwitchId

An NDIS_NIC_SWITCH_ID value that represents the NIC switch where the VPort resides. 

The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch. 


### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value that represents the VPort identifier.


### -field Flags

A <b>ULONG</b> value that contains a bitwise OR of flags. This member qualifies the information in this structure.

Possible flags are as follows:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR"></a><a id="ndis_rss_set_indirection_entry_flag_primary_processor"></a><dl>
<dt><b>NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the primary processor of the scaling entity (in other words, a VPort in RSSv2 mode). The indirection table is not used.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR"></a><a id="ndis_rss_set_indirection_entry_flag_default_processor"></a><dl>
<dt><b>NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the default processor of the scaling entity (in other words, a VPort in RSSv2 mode). The indirection table is not used.

</td>
</tr>
</table>
 


### -field IndirectionTableIndex

A <b>USHORT</b> value that indicates the indirection table entry being moved.


### -field TargetProcessorNumber

The target processor number.


### -field EntryStatus

An NDIS_STATUS code indicating the status of the move operation for this entry. Because <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is used in the context of a Synchronous OID call, the miniport driver cannot return <b>NDIS_STATUS_PENDING</b> for this member.


## -see-also




<a href="https://msdn.microsoft.com/9AB69EC6-FE78-4242-89C7-D36AA16676BF">NDIS_RSS_SET_INDIRECTION_ENTRIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">Receive Side Scaling Version 2 (RSSv2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID request interface in NDIS 6.80</a>
 

 

