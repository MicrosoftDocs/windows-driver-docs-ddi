---
UID: NS:ntddndis._NDIS_RSS_SET_INDIRECTION_ENTRIES
title: "_NDIS_RSS_SET_INDIRECTION_ENTRIES"
author: windows-driver-content
description: The NDIS_RSS_SET_INDIRECTION_ENTRIES structure represents a set of actions, where each action moves a single entry of the Receive Side Scaling (RSS) indirection table of a specified VPort to a specified target CPU.
old-location: netvista\ndis_rss_set_indirection_entries.htm
old-project: netvista
ms.assetid: 9AB69EC6-FE78-4242-89C7-D36AA16676BF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_RSS_SET_INDIRECTION_ENTRIES structure pointer [Network Drivers Starting with Windows Vista], NDIS_RSS_SET_INDIRECTION_ENTRIES, ntddndis/NDIS_RSS_SET_INDIRECTION_ENTRIES, _NDIS_RSS_SET_INDIRECTION_ENTRIES, NDIS_RSS_SET_INDIRECTION_ENTRIES structure [Network Drivers Starting with Windows Vista], *PNDIS_RSS_SET_INDIRECTION_ENTRIES, ntddndis/PNDIS_RSS_SET_INDIRECTION_ENTRIES, netvista.ndis_rss_set_indirection_entries, PNDIS_RSS_SET_INDIRECTION_ENTRIES
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RSS_SET_INDIRECTION_ENTRIES
product: Windows
targetos: Windows
req.typenames: "*PNDIS_RSS_SET_INDIRECTION_ENTRIES, NDIS_RSS_SET_INDIRECTION_ENTRIES"
---

# _NDIS_RSS_SET_INDIRECTION_ENTRIES structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
<div class="alert"><b>Warning</b>  RSSv2 is preview only in Windows 10, version 1709.</div><div> </div>The <b>NDIS_RSS_SET_INDIRECTION_ENTRIES</b> structure represents a set of actions, where each action moves a single entry of the Receive Side Scaling (RSS) indirection table of a specified VPort to a specified target CPU. It is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a> OID, which is a <a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID</a> for <a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">RSS Version 2 (RSSv2)</a>.


## -syntax


````
typedef struct _NDIS_RSS_SET_INDIRECTION_ENTRIES {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              RssEntrySize;
  ULONG              RssEntryTableOffset;
  ULONG              NumberOfRssEntries;
} NDIS_RSS_SET_INDIRECTION_ENTRIES, *PNDIS_RSS_SET_INDIRECTION_ENTRIES;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RSS_SET_INDIRECTION_ENTRIES</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>. 

For NDIS  6.80 and later drivers, set the 
     <b>Revision</b> member to <b>NDIS_RSS_SET_INDIRECTION_ENTRIES_REVISION_1</b> and the 
     <b>Size</b> member to <b>sizeof(NDIS_RSS_SET_INDIRECTION_ENTRIES)</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise OR of flags. This member qualifies the other members of this structure, as well as the array processing policy. In Windows 10, version 1709, no flags are defined for this member.


### -field RssEntrySize

An opaque number that needs to be added to the pointer during array traversal.


### -field RssEntryTableOffset

The offset of the <a href="..\ntddndis\ns-ntddndis-_ndis_rss_set_indirection_entry.md">NDIS_RSS_SET_INDIRECTION_ENTRY</a> array from the beginning of this structure.


### -field NumberOfRssEntries

The number of formatted <a href="..\ntddndis\ns-ntddndis-_ndis_rss_set_indirection_entry.md">NDIS_RSS_SET_INDIRECTION_ENTRY</a> structures in the array.


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/receive-side-scaling-version-2-rssv2-">Receive Side Scaling Version 2 (RSSv2)</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_capabilities.md">NDIS_NIC_SWITCH_CAPABILITIES</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_rss_set_indirection_entry.md">NDIS_RSS_SET_INDIRECTION_ENTRY</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID request interface in NDIS 6.80</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-rss-set-indirection-table-entries">OID_GEN_RSS_SET_INDIRECTION_TABLE_ENTRIES</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RSS_SET_INDIRECTION_ENTRIES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

