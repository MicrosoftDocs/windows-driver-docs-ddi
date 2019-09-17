---
UID: NS:windot11._DOT11_PEER_STATISTICS
title: _DOT11_PEER_STATISTICS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_peer_statistics.htm
tech.root: netvista
ms.assetid: 08ea7f19-e086-4d5a-bfc7-de9178d815cd
ms.date: 02/16/2018
ms.keywords: "*PDOT11_PEER_STATISTICS, DOT11_PEER_STATISTICS, DOT11_PEER_STATISTICS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5e07a8dd-79f1-4cba-89d3-f70e04caad12.xml, PDOT11_PEER_STATISTICS, PDOT11_PEER_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PEER_STATISTICS, netvista.dot11_peer_statistics, windot11/DOT11_PEER_STATISTICS, windot11/PDOT11_PEER_STATISTICS"
ms.topic: struct
f1_keywords:
 - "windot11/DOT11_PEER_STATISTICS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
- windot11.h
api_name:
- DOT11_PEER_STATISTICS
targetos: Windows
req.typenames: DOT11_PEER_STATISTICS, *PDOT11_PEER_STATISTICS
product:
- Windows 10 or later.
---

# _DOT11_PEER_STATISTICS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PEER_STATISTICS structure records statistical counters for the IEEE media access control
  (MAC) sublayer of a peer station within an independent basic service set (IBSS) network.
<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="https://docs.microsoft.com/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div><div> </div>

## -syntax


```cpp
typedef struct _DOT11_PEER_STATISTICS {
  ULONGLONG ullDecryptSuccessCount;
  ULONGLONG ullDecryptFailureCount;
  ULONGLONG ullTxPacketSuccessCount;
  ULONGLONG ullTxPacketFailureCount;
  ULONGLONG ullRxPacketSuccessCount;
  ULONGLONG ullRxPacketFailureCount;
} DOT11_PEER_STATISTICS, *PDOT11_PEER_STATISTICS;
```


## -struct-fields




### -field ullDecryptSuccessCount

The number of received encrypted packets that the peer station successfully decrypted.


### -field ullDecryptFailureCount

The number of encrypted packets that the peer station failed to decrypt.


### -field ullTxPacketSuccessCount

The number of MAC service data unit (MSDU) packets and MAC management protocol data unit (MMPDU)
     frames that the IEEE MAC sublayer of the peer station successfully transmitted.


### -field ullTxPacketFailureCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the peer station
     attempted to transmit, but that failed to transmit.


### -field ullRxPacketSuccessCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the peer station
     successfully received.


### -field ullRxPacketFailureCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the peer station
     attempted to receive, but that failed to be received.


## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 


