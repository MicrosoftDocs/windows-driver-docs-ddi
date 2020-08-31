---
UID: NS:ntddndis._NDIS_RSS_SET_INDIRECTION_ENTRIES
title: _NDIS_RSS_SET_INDIRECTION_ENTRIES (ntddndis.h)
description: The NDIS_RSS_SET_INDIRECTION_ENTRIES structure represents a set of actions, where each action moves a single entry of the Receive Side Scaling (RSS) indirection table of a specified VPort to a specified target CPU.
old-location: netvista\ndis_rss_set_indirection_entries.htm
tech.root: netvista
ms.assetid: 9AB69EC6-FE78-4242-89C7-D36AA16676BF
ms.date: 05/02/2018
keywords: ["NDIS_RSS_SET_INDIRECTION_ENTRIES structure"]
ms.keywords: "*PNDIS_RSS_SET_INDIRECTION_ENTRIES, NDIS_RSS_SET_INDIRECTION_ENTRIES, NDIS_RSS_SET_INDIRECTION_ENTRIES structure [Network Drivers Starting with Windows Vista], PNDIS_RSS_SET_INDIRECTION_ENTRIES, PNDIS_RSS_SET_INDIRECTION_ENTRIES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSS_SET_INDIRECTION_ENTRIES, netvista.ndis_rss_set_indirection_entries, ntddndis/NDIS_RSS_SET_INDIRECTION_ENTRIES, ntddndis/PNDIS_RSS_SET_INDIRECTION_ENTRIES"
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
targetos: Windows
req.typenames: NDIS_RSS_SET_INDIRECTION_ENTRIES, *PNDIS_RSS_SET_INDIRECTION_ENTRIES
f1_keywords:
 - _NDIS_RSS_SET_INDIRECTION_ENTRIES
 - ntddndis/_NDIS_RSS_SET_INDIRECTION_ENTRIES
 - PNDIS_RSS_SET_INDIRECTION_ENTRIES
 - ntddndis/PNDIS_RSS_SET_INDIRECTION_ENTRIES
 - NDIS_RSS_SET_INDIRECTION_ENTRIES
 - ntddndis/NDIS_RSS_SET_INDIRECTION_ENTRIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RSS_SET_INDIRECTION_ENTRIES
---

# _NDIS_RSS_SET_INDIRECTION_ENTRIES structure


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> RSSv2 is preview only in Windows 10, version 1803.

The <b>NDIS_RSS_SET_INDIRECTION_ENTRIES</b> structure represents a set of actions, where each action moves a single entry of the Receive Side Scaling (RSS) indirection table of a specified VPort to a specified target CPU. It is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a> OID, which is a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID</a> for <a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RSS_SET_INDIRECTION_ENTRIES</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RSS_SET_INDIRECTION_ENTRIES</b>. 

For NDIS  6.80 and later drivers, set the 
     <b>Revision</b> member to <b>NDIS_RSS_SET_INDIRECTION_ENTRIES_REVISION_1</b> and the 
     <b>Size</b> member to <b>sizeof(NDIS_RSS_SET_INDIRECTION_ENTRIES)</b>.

### -field Flags

A <b>ULONG</b> value that contains a bitwise OR of flags. This member qualifies the other members of this structure, as well as the array processing policy. In Windows 10, version 1803, no flags are defined for this member.

### -field RssEntrySize

An opaque number that needs to be added to the pointer during array traversal.

### -field RssEntryTableOffset

The offset of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_set_indirection_entry">NDIS_RSS_SET_INDIRECTION_ENTRY</a> array from the beginning of this structure.

### -field NumberOfRssEntries

The number of formatted <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_set_indirection_entry">NDIS_RSS_SET_INDIRECTION_ENTRY</a> structures in the array.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_nic_switch_capabilities">NDIS_NIC_SWITCH_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_set_indirection_entry">NDIS_RSS_SET_INDIRECTION_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">Receive Side Scaling Version 2 (RSSv2)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID request interface in NDIS 6.80</a>

