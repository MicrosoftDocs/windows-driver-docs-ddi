---
UID: NS:ntddndis._NDIS_HD_SPLIT_CURRENT_CONFIG
title: "_NDIS_HD_SPLIT_CURRENT_CONFIG"
author: windows-driver-content
description: The NDIS_HD_SPLIT_CURRENT_CONFIG structure provides the current header-data split configuration of a miniport adapter.
old-location: netvista\ndis_hd_split_current_config.htm
tech.root: netvista
ms.assetid: 866fe9e6-0cb1-45cd-84b4-4e2df9c9c45a
ms.date: 5/2/2018
ms.keywords: "*PNDIS_HD_SPLIT_CURRENT_CONFIG, NDIS_HD_SPLIT_CURRENT_CONFIG, NDIS_HD_SPLIT_CURRENT_CONFIG structure [Network Drivers Starting with Windows Vista], PNDIS_HD_SPLIT_CURRENT_CONFIG, PNDIS_HD_SPLIT_CURRENT_CONFIG structure pointer [Network Drivers Starting with Windows Vista], _NDIS_HD_SPLIT_CURRENT_CONFIG, header_data_split_ref_7275dcfc-6fe4-4648-9b4c-0b5a37aa850b.xml, netvista.ndis_hd_split_current_config, ntddndis/NDIS_HD_SPLIT_CURRENT_CONFIG, ntddndis/PNDIS_HD_SPLIT_CURRENT_CONFIG"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	ntddndis.h
api_name:
-	NDIS_HD_SPLIT_CURRENT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: NDIS_HD_SPLIT_CURRENT_CONFIG, *PNDIS_HD_SPLIT_CURRENT_CONFIG
---

# _NDIS_HD_SPLIT_CURRENT_CONFIG structure


## -description


The NDIS_HD_SPLIT_CURRENT_CONFIG structure provides the current header-data split configuration of a
  miniport adapter.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_HD_SPLIT_CURRENT_CONFIG structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_HD_SPLIT_CURRENT_CONFIG_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_HD_SPLIT_CURRENT_CONFIG_REVISION_1.


### -field HardwareCapabilities

The header-data split hardware capabilities that the miniport adapter supports. These capabilities
     should include capabilities that are currently disabled by INF file settings or through the 
     <b>Advanced</b> properties page. The value of 
     <b>HardwareCapabilities</b> is a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_CAPS_SUPPORTS_HEADER_DATA_SPLIT

The miniport adapter can split the header and data into separate memory descriptor lists (MDLs)
       that meet the requirements for header-data split support.



#### NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV4_OPTIONS

The miniport adapter can split IPv4 Ethernet frames that include IPv4 options. The miniport
       adapter can support splitting some IPv4 options while not splitting others. 
       

<div class="alert"><b>Note</b>  The NIC must not split IPv4 frames that contain unsupported IPv4 options. If an
       IPv4 frame is split, the header portion of the split frame must contain the entire IPv4 header and all
       of the IPv4 options that are present.</div>
<div> </div>


#### NDIS_HD_SPLIT_CAPS_SUPPORTS_IPV6_EXTENSION_HEADERS

The miniport adapter can split IPv6 Ethernet frames that include IPv6 extension headers. The
       miniport adapter can support some IPv6 extension headers while not supporting others. 
       

<div class="alert"><b>Note</b>  The NIC must not split IPv6 frames that contain unsupported IPv6 extension
       headers. If an IPv6 frame is split, the header portion of the split frame must contain the entire IPv6
       header and all of the IPv6 extension headers that are present.</div>
<div> </div>


#### NDIS_HD_SPLIT_CAPS_SUPPORTS_TCP_OPTIONS

The miniport adapter can split TCP frames with other TCP options in addition to the timestamp
       option. The miniport adapter can support some TCP options and not support others.
       

<div class="alert"><b>Note</b>  If the only TCP option in a frame is the timestamp option, the data-split
       provider must be able to split the frame.</div>
<div> </div>
<div class="alert"><b>Note</b>  If a TCP header contains an unsupported TCP option, the NIC must split the frame
       at the beginning of the TCP header or must not split the frame.</div>
<div> </div>

### -field CurrentCapabilities

The current header-data split capabilities that the miniport adapter supports. The miniport driver
     uses the same flags that are defined for the 
     <b>HardwareCapabilities</b> member. In this case, the flags are set to indicate the current capabilities
     that depend on the current configuration settings.


### -field HDSplitFlags

A set of flags that reports the status of header-data split for a miniport adapter. NDIS sets this
     member with a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_ENABLE_HEADER_DATA_SPLIT

The miniport driver has enabled header-data split in the hardware. Otherwise, header-data split
       is disabled.


### -field HDSplitCombineFlags

A set of flags that specify the current header-data split settings of a miniport adapter. The
     value of 
     <b>HDSplitCombineFlags</b> can be a bitwise OR of the following flags:
     





#### NDIS_HD_SPLIT_COMBINE_ALL_HEADERS

The miniport adapter is combining split frames. If header-data split is enabled in the hardware,
       the miniport driver should combine the header and data before indicating the frame to NDIS.


### -field BackfillSize

The backfill size, in bytes, that the miniport driver is using for the data portion of a split
     frame.


### -field MaxHeaderSize

The maximum size, in bytes, that the miniport driver is using for the header portion of a split
     frame. 
     

<div class="alert"><b>Note</b>  If the length of a header exceeds 
     <b>MaxHeaderSize</b> because of the presence of IPv4 options, IPsec headers, or IPv6 extension headers,
     the frame must not be split. If a header that includes a TCP or UDP header exceeds 
     <b>MaxHeaderSize</b> because of the presence of TCP header, TCP options, or UDP header, the NIC must
     split the frame at the beginning of the upper layer protocol header or must not split the
     frame.</div>
<div> </div>

## -remarks



The NDIS_HD_SPLIT_CURRENT_CONFIG structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-hd-split-current-config">
    OID_GEN_HD_SPLIT_CURRENT_CONFIG</a> OID query request to obtain the current header-data split
    configuration of a miniport adapter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-hd-split-current-config">OID_GEN_HD_SPLIT_CURRENT_CONFIG</a>
 

 

