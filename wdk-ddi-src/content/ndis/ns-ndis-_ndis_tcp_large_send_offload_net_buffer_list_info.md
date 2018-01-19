---
UID: NS:ndis._NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO
title: _NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO
author: windows-driver-content
description: The NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO structure specifies information that is used in offloading large send offload (LSO) tasks from the TCP/IP transport to a miniport adapter.
old-location: netvista\ndis_tcp_large_send_offload_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 48827a51-d364-43f6-864b-b63395168429
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO, NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO, *PNDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.typenames: NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO, *PNDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO
---

# _NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO structure



## -description
The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure specifies information that is used in
  offloading large send offload (LSO) tasks from the TCP/IP transport to a miniport adapter. The
  <b>NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure is part of the 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> information.



## -syntax

````
typedef struct _NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO {
  union {
    struct {
      ULONG Unused  :30;
      ULONG Type  :1;
      ULONG Reserved2  :1;
    } Transmit;
    struct {
      ULONG MSS  :20;
      ULONG TcpHeaderOffset  :10;
      ULONG Type  :1;
      ULONG Reserved2  :1;
    } LsoV1Transmit;
    struct {
      ULONG TcpPayload  :30;
      ULONG Type  :1;
      ULONG Reserved2  :1;
    } LsoV1TransmitComplete;
    struct {
      ULONG MSS  :20;
      ULONG TcpHeaderOffset  :10;
      ULONG Type  :1;
      ULONG IPVersion  :1;
    } LsoV2Transmit;
    struct {
      ULONG Reserved  :30;
      ULONG Type  :1;
      ULONG Reserved2  :1;
    } LsoV2TransmitComplete;
    PVOID  Value;
  };
} NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO, *PNDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO;
````


## -struct-fields

### -field Transmit

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO that specifies transmit
      information and that contains the following members:
      


### -field Unused

A ULONG value that specifies unused space that is reserved for NDIS.


### -field Type

The offload type that the miniport driver should run. Protocol drivers set this member to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V1_TYPE to specify large send offload version 1 (LSOV1) operations or to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V2_TYPE to specify large send offload version 2 (LSOV2)
        operations.


### -field Reserved2

Reserved for NDIS.

</dd>
</dl>

### -field LsoV1Transmit

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO that specifies LSO transmit
      information and that contains the following members:
      


### -field MSS

The maximum segment size (MSS), in bytes, for each packet after segmentaion. The TCP/IP
        transport writes this value before passing a large TCP packet to a miniport driver for segmentation.
        The size of TCP payload in each transmitted segment must not exceed this value.


### -field TcpHeaderOffset

The offset, in bytes, of the TCP header from the beginning of the packet for TCP packets.
        Miniport drivers can use 
        <b>TcpHeaderOffset</b> to determine the location of the TCP header so that they do not have to parse
        IP headers.


### -field Type

The offload type that the miniport driver should run. Protocol drivers set this member to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V1_TYPE to specify LSOV1 operations or to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V2_TYPE to specify LSOV2 operations.


### -field Reserved2

Reserved for NDIS.

</dd>
</dl>

### -field LsoV1TransmitComplete

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO that specifies LSO transmit
      complete information and that contains the following members:
      


### -field TcpPayload

The total number of TCP payload bytes in a set of packets that a network interface card (NIC)
        created by segmenting a large packet. A miniport driver writes the TCP payload size before completing
        the send of an LSO packet.


### -field Type

The offload type that the miniport driver performed. The mniport drivers leaves this value the
        same as it was when the overlying driver submitted the packet for transmit.


### -field Reserved2

Reserved for NDIS.

</dd>
</dl>

### -field LsoV2Transmit

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO that specifies LSOV2 transmit
      information and that contains the following members:
      


### -field MSS

The MSS, in bytes, for each TCP segment. The TCP/IP transport writes this value before passing
        a large TCP packet to a miniport driver for segmentation.


### -field TcpHeaderOffset

The offset, in bytes, of the TCP header from the beginning of the packet for TCP packets.
        Miniport drivers can use 
        <b>TcpHeaderOffset</b> to determine the location of the TCP header so that they do not have to parse
        IP headers.


### -field Type

The offload type that the miniport driver should run. Protocol drivers set this member to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V1_TYPE to specify LSOV1 operations or to
        NDIS_TCP_LARGE_SEND_OFFLOAD_V2_TYPE to specify LSOV2 operations.


### -field IPVersion

The IP version of the packet. For IPv4 packets, 
        <b>IPVersion</b> is set to NDIS_TCP_LARGE_SEND_OFFLOAD_IPv4. For IPv6 packets, 
        <b>IPVersion</b> is set to NDIS_TCP_LARGE_SEND_OFFLOAD_IPv6.

</dd>
</dl>

### -field LsoV2TransmitComplete

A structure within NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO that specifies LSOV2 transmit
      complete information and that contains the following members:
      


### -field Reserved

In general, this member is reserved for NDIS.  However, when a send operation is complete, the miniport driver must set this member to zero.


### -field Type

The offload type that the miniport driver performed. The mniport driver leaves this value the
        same as it was when the overlying driver submitted the packet for transmit.

 For example, when a send operation is complete, the miniport driver sets this member to <b>NDIS_TCP_LARGE_SEND_OFFLOAD_V2_TYPE</b>.


### -field Reserved2

Reserved for NDIS.

</dd>
</dl>

### -field Value

A PVOID version of the LSO information. Use this member to access the raw information instead of
      the specific fields.


## -remarks
The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure specifies information for LSOV1 and
    LSOV2 operations. The <b>NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure is part of the
    information that is included in a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

To set and get the LSOV1 or LSOV2 information, use the 
    <b>TcpLargeSendNetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    <b>NET_BUFFER_LIST_INFO</b> returns a ULONG value (not a pointer to a ULONG value).

The TCP/IP transport updates the 
    <b>MSS</b> and 
    <b>TcpHeaderOffset</b> members of the <b>NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO</b> structure before
    sending a large packet to a miniport driver.

For LSOV1, miniport drivers write the TCP payload size in the 
    <b>TcpPayload</b> member before completing a send operation for a segmented packet.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/network/offloading-the-segmentation-of-large-tcp-packets">Offloading the Segmentation of Large TCP Packets</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_LARGE_SEND_OFFLOAD_NET_BUFFER_LIST_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

