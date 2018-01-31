---
UID: NS:windot11.DOT11_EXTSTA_RECV_CONTEXT
title: DOT11_EXTSTA_RECV_CONTEXT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_extsta_recv_context.htm
old-project: netvista
ms.assetid: 517be11b-a15d-43ac-aefd-f425fa6f63e7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_EXTSTA_RECV_CONTEXT, *PDOT11_EXTAP_RECV_CONTEXT, DOT11_EXTSTA_RECV_CONTEXT structure [Network Drivers Starting with Windows Vista], netvista.dot11_extsta_recv_context, PDOT11_EXTSTA_RECV_CONTEXT, DOT11_EXTAP_RECV_CONTEXT, PDOT11_EXTSTA_RECV_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], *PDOT11_EXTSTA_RECV_CONTEXT, windot11/DOT11_EXTSTA_RECV_CONTEXT, windot11/PDOT11_EXTSTA_RECV_CONTEXT, Native_802.11_data_types_c3f69d82-f4b2-4a2a-b864-9b4eebc9e3ff.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	windot11.h
apiname:
-	DOT11_EXTSTA_RECV_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PDOT11_EXTSTA_RECV_CONTEXT, DOT11_EXTSTA_RECV_CONTEXT, DOT11_EXTAP_RECV_CONTEXT, *PDOT11_EXTAP_RECV_CONTEXT"
req.product: Windows 10 or later.
---

# DOT11_EXTSTA_RECV_CONTEXT structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_EXTSTA_RECV_CONTEXT structure defines the Native 802.11 attributes of a received packet by
  the 802.11 station and indicated by the miniport driver operating in either Extensible Station (ExtSTA) or
  Network Monitor (NetMon) modes. For more information about these operation modes, see 
  <mshelp:link keywords="netvista.native_802_11_operation_modes" tabindex="0">Native 802.11 Operation
  Modes</mshelp:link>.


## -syntax


````
typedef struct DOT11_EXTSTA_RECV_CONTEXT {
  NDIS_OBJECT_HEADER Header;
  ULONG              uReceiveFlags;
  ULONG              uPhyId;
  ULONG              uChCenterFrequency;
  USHORT             usNumberOfMPDUsReceived;
  LONG               lRSSI;
  UCHAR              ucDataRate;
  ULONG              uSizeMediaSpecificInfo;
  PVOID              pvMediaSpecificInfo;
  ULONGLONG          ullTimestamp;
} DOT11_EXTSTA_RECV_CONTEXT, *PDOT11_EXTSTA_RECV_CONTEXT;
````


## -struct-fields




#### - Header

The type, revision, and size of the DOT11_EXTSTA_RECV_CONTEXT structure. This member is formatted
     as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:



For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


#### Revision

This member must be set to DOT11_EXTSTA_RECV_CONTEXT_REVISION_1.


#### Size

This member must be set to 
       sizeof(DOT11_EXTSTA_RECV_CONTEXT).


#### - uReceiveFlags

The attributes of the received packet data specified through a bitmask. 
     

If the miniport driver is operating in ExtSTA mode, the driver must always set 
     <b>uReceiveFlags</b> to zero.

The following flag values are valid for the miniport driver if is operating in NetMon mode.




#### DOT11_RECV_FLAG_RAW_PACKET

If this bit is set, the packet contains the data as it was originally received by the 802.11
       station. For more information about raw packets, see 
       <mshelp:link keywords="netvista.indicating_raw_802_11_packets" tabindex="0">Indicating Raw 802.11
       Packets</mshelp:link>.


#### DOT11_RECV_FLAG_RAW_PACKET_FCS_FAILURE

If this bit is set, the raw packet data was received with frame check sequence (FCS) failures.
       
<div class="alert"><b>Note</b>  The miniport driver must set DOT11_RECV_FLAG_RAW_PACKET when setting
       DOT11_RECV_FLAG_RAW_PACKET_FCS_FAILURE.</div><div> </div>

#### DOT11_RECV_FLAG_RAW_PACKET_TIMESTAMP

If this bit is set, the NIC sets the timestamp information in the 
       <b>ullTimestamp</b> member.


#### - uPhyId

The identifier (ID) of the PHY on which the 802.11 station received the packet.


#### - uChCenterFrequency

The channel center frequency, in units of megahertz (MHz), of the frequency band on which the
     802.11 station received the packet.


#### - usNumberOfMPDUsReceived

The number of media access control (MAC) protocol data unit (MPDU) fragments received and
     reassembled by the 802.11 station for the packet. The value of 
     <b>usNumberOfMPDUsReceived</b> must be from one through the value of DOT11_MAX_NUM_OF_FRAGMENTS.


#### - lRSSI

The received signal strength indication (RSSI) value for the last received MPDU fragment of the
     802.11 packet. The RSSI value is in units of decibels referenced to 1.0 milliwatts (dBm).


#### - ucDataRate

The data rate at which the 802.11 station received the packet. The value of 
     <b>ucDataRate</b> is the value of the 
     <b>ucDataRateIndex</b> member of the data rate from the 802.11 station's data rate mapping table. For
     more information about the data rate mapping table, see 
     <mshelp:link keywords="netvista.oid_dot11_data_rate_mapping_table" tabindex="0">
     OID_DOT11_DATA_RATE_MAPPING_TABLE</mshelp:link>.


#### - uSizeMediaSpecificInfo

The size, in bytes, of the media specific information at the 
     <b>pvMediaSpecificInfo</b> member. 
     <b>uSizeMediaSpecificInfo</b> supports copying of the media-specific information and passing it to an IHV
     extension.
     
<div class="alert"><b>Note</b>  This member is currently reserved for future use and must contain
     zero.</div><div> </div>

#### - pvMediaSpecificInfo

A pointer to a buffer that contains media-specific infomration. The mininiport driver can set this
     member if the miniport driver passes media-specific OOB data to an IHV-specific 802.3 protocol driver.
     

The native 802.11 framework copies this pointer to the 
     <b>MediaSpecificInformation</b> entry at the 
     <b>NetBufferListInfo</b> member of the 802.3 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures in NDIS receive
     indications.
<div class="alert"><b>Note</b>  IHV extensions are currently unable to receive the 
     <b>MediaSpecificInformation</b>.</div><div> </div>

#### - ullTimestamp

An 802.11 timing synchronization function (TSF) timer value, in microseconds, that specifies the
     time when the packet was received. This member is provided to support 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/indicating-raw-802-11-packets">indicating raw 802.11 packets</a>.
     

If a NIC does not support 
     <b>ullTimestamp</b>, it must not set the DOT11_RECV_FLAG_RAW_PACKET_TIMESTAMP flag in the 
     <b>uReceiveFlags</b> member.


## -remarks


When performing a Native 802.11 receive operation, the miniport driver must format each received
    802.11 packet as a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure, with the packet
    data formatted as a 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure and linked to the
    NET_BUFFER_LIST structure. Each NET_BUFFER_LIST structure must include out-of-band (OOB) data. The OOB
    data specifies the attributes of the received packet that are specific to the wireless LAN (WLAN)
    media.

The miniport driver accesses the Native 802.11 OOB data through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with the
    following parameters:
<ul>
<li>
The 
      <i>_NBL</i> parameter, which is passed the pointer to the 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure used for the
      received 802.11 packet.

</li>
<li>
The _
      <i>id</i> parameter, which is passed the identifier (ID) value of 
      <b>MediaSpecificInformation</b>.

</li>
</ul>If the miniport driver sets DOT11_RECV_FLAG_RAW_PACKET in the 
    <b>uReceiveFlags</b> member, the driver must follow these guidelines when preparing the
    DOT11_EXTSTA_RECV_CONTEXT structure:
<ul>
<li>
Set the value of 
      <b>usNumberOfMPDUsReceived</b> to one.

</li>
<li>
Set the value of 
      <b>lRSSI</b> to the RSSI value for the raw packet itself.

</li>
<li>
Set the value of 
      <b>ucDataRate</b> to the 
      <b>ucDataRateIndex</b> value for the raw packet itself.

</li>
<li>
Set the value of 
      <b>ucRSSI</b> to the normalized RSSI value for the raw packet itself.

</li>
</ul>For more information about raw packets, see 
    <mshelp:link keywords="netvista.indicating_raw_802_11_packets" tabindex="0">Indicating Raw 802.11
    Packets</mshelp:link>.

For more information about Native 802.11 receive operations, see 
    <mshelp:link keywords="netvista.native_802_11_receive_operations" tabindex="0">Native 802.11 Receive
    Operations</mshelp:link>.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.ndismindicatereceivenetbufferlists" tabindex="0"><b>
   NdisMIndicateReceiveNetBufferLists</b></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.oid_dot11_data_rate_mapping_table" tabindex="0">
   OID_DOT11_DATA_RATE_MAPPING_TABLE</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_EXTSTA_RECV_CONTEXT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

