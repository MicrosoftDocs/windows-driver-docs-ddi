---
UID: NS:windot11._DOT11_PEER_STATISTICS
title: _DOT11_PEER_STATISTICS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_peer_statistics.htm
old-project: netvista
ms.assetid: 08ea7f19-e086-4d5a-bfc7-de9178d815cd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_PEER_STATISTICS, DOT11_PEER_STATISTICS, *PDOT11_PEER_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_PEER_STATISTICS
req.alt-loc: windot11.h
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
req.typenames: DOT11_PEER_STATISTICS, *PDOT11_PEER_STATISTICS
req.product: Windows 10 or later.
---

# _DOT11_PEER_STATISTICS structure



## -description

## -syntax

````
typedef struct _DOT11_PEER_STATISTICS {
  ULONGLONG ullDecryptSuccessCount;
  ULONGLONG ullDecryptFailureCount;
  ULONGLONG ullTxPacketSuccessCount;
  ULONGLONG ullTxPacketFailureCount;
  ULONGLONG ullRxPacketSuccessCount;
  ULONGLONG ullRxPacketFailureCount;
} DOT11_PEER_STATISTICS, *PDOT11_PEER_STATISTICS;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PEER_STATISTICS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

