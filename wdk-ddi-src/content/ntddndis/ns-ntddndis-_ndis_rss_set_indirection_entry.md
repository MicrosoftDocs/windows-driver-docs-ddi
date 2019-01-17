---
UID: NS:ntddndis._NDIS_RSS_SET_INDIRECTION_ENTRY
title: "_NDIS_RSS_SET_INDIRECTION_ENTRY"
description: The NDIS_RSS_SET_INDIRECTION_ENTRY structure represents a command to set a single indirection table entry.
old-location: netvista\ndis_rss_set_indirection_entry.htm
tech.root: netvista
ms.assetid: 4430E19F-C603-4C52-8FC8-C36197FD2996
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RSS_SET_INDIRECTION_ENTRY, NDIS_RSS_SET_INDIRECTION_ENTRY, NDIS_RSS_SET_INDIRECTION_ENTRY structure [Network Drivers Starting with Windows Vista], NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR, NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_PRIMARY_PROCESSOR, PNDIS_RSS_SET_INDIRECTION_ENTRY, PNDIS_RSS_SET_INDIRECTION_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSS_SET_INDIRECTION_ENTRY, netvista.ndis_rss_set_indirection_entry, ntddndis/NDIS_RSS_SET_INDIRECTION_ENTRY, ntddndis/PNDIS_RSS_SET_INDIRECTION_ENTRY"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RSS_SET_INDIRECTION_ENTRY
product:
- Windows
targetos: Windows
req.typenames: NDIS_RSS_SET_INDIRECTION_ENTRY, *PNDIS_RSS_SET_INDIRECTION_ENTRY
---

# _NDIS_RSS_SET_INDIRECTION_ENTRY structure


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> RSSv2 is preview only in Windows 10, version 1803.


The <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> structure represents a command to set a single indirection table entry. It is contained in an <a href="https://msdn.microsoft.com/9AB69EC6-FE78-4242-89C7-D36AA16676BF">NDIS_RSS_SET_INDIRECTION_ENTRIES</a> structure, which is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a> OID. OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES is a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID</a> for <a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>.


## -struct-fields




### -field SwitchId

An NDIS_NIC_SWITCH_ID value that represents the NIC switch where the VPort resides. 

The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch. 

This field should be set to **0** in the Native RSS case.


### -field VPortId

An NDIS_NIC_SWITCH_VPORT_ID value that represents the VPort identifier.

This field should be set to **0** in the Native RSS case.


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
Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the primary processor of the scaling entity. The indirection table is not used. When the primary processor is *inactive* (RSS is enabled), the miniport driver should track updates to entries with this flag set so it knows which processor will be the primary when RSS is disabled.

</td>
</tr>
<tr>
<td width="40%"><a id="NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR"></a><a id="ndis_rss_set_indirection_entry_flag_default_processor"></a><dl>
<dt><b>NDIS_RSS_SET_INDIRECTION_ENTRY_FLAG_DEFAULT_PROCESSOR</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is referring to the default processor of the scaling entity. The default processor handles unhashed packets. The indirection table is not used. When the default processor is *inactive* (RSS is disabled), the miniport driver should track updates to entries with this flag set so it knows which processor will be default when RSS is enabled.

</td>
</tr>
</table>
 


### -field IndirectionTableIndex

The hash index of the ITE that currently points to the current CPU and is being modified to point to another processor. When the indirection table is *inactive* (RSS is disabled), the miniport driver should track updates to indirection table entries so it has the correct indirection table when RSS is enabled.


### -field TargetProcessorNumber

The target processor number to which the ITE should point upon completion. The miniport driver should succeed ITE moves from current to current processor.


### -field EntryStatus

An NDIS_STATUS code indicating the status of the move operation for this entry. Because <b>NDIS_RSS_SET_INDIRECTION_ENTRY</b> is used in the context of a Synchronous OID call, the miniport driver cannot return <b>NDIS_STATUS_PENDING</b> for this member.

To simplify miniport drivers' implementation, the upper layer protocol will initialize this field to NDIS_STATUS_PENDING. Miniport drivers must overwrite NDIS_STATUS_PENDING with either a success or failure NDIS status code. If the upper layer detects that this field is still NDIS_STATUS_PENDING upon completion of the [OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES](https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries) OID, it will cause a system bug check and indicate that the miniport driver is at fault.

> [!IMPORTANT]
> All **NDIS_RSS_SET_INDIRECTION_ENTRY** structures in a group, contained in an [**NDIS_RSS_SET_INDIRECTION_ENTRIES**](ns-ntddndis-_ndis_rss_set_indirection_entries.md) structure, must be marked with the same **EntryStatus**.

If an error occurs with this move command, set **EntryStatus** to one of the following status codes for that error condition:

| Status code | Error condition |
| --- | --- |
| NDIS_STATUS_INVALID_PARAMETER | <ul><li>The **SwitchId** or **VPortId** member was invalid.</li><li>The **Flags** member was invalid.</li><li>The **IndirectionTableIndex** member exceeds the currently configured **NumberOfIndirectionTableEntries** from the [**NDIS_RECEIVE_SCALE_PARAMETERS_V2**](ns-ntddndis-_ndis_receive_scale_parameters_v2.md) structure.</li></ul> |
| NDIS_STATUS_INVALID_PORT_STATE | The VPort is not activated or is in some other state that prevents it from accepting RSSv2 OIDs. |
| NDIS_STATUS_NOT_ACCEPTED | The actor CPU was invalid. |
| NDIS_STATUS_INVALID_DATA | For an *active* steering parameter, the new processor is not part of the adapter's RSS processor set. Note that *inactive* parameters only need to be tracked. They are validated later, during RSS state transition (to *on* or *off*). |
| NDIS_STATUS_NO_QUEUES | A group of command entries fails the "number of queues" check for the VPort specified by that group. |

## -see-also




<a href="https://msdn.microsoft.com/9AB69EC6-FE78-4242-89C7-D36AA16676BF">NDIS_RSS_SET_INDIRECTION_ENTRIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">Receive Side Scaling Version 2 (RSSv2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID request interface in NDIS 6.80</a>
 

 

