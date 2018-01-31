---
UID: NS:iscsiprf._MSiSCSI_QMIPSECStats
title: "_MSiSCSI_QMIPSECStats"
author: windows-driver-content
description: The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA.
old-location: storage\msiscsi_qmipsecstats.htm
old-project: storage
ms.assetid: 265ed956-1065-44be-ac8e-94bab2e4e8b8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: iscsiprf/PMSiSCSI_QMIPSECStats, PMSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats, structs-iSCSI_979ce8ac-35be-4ac1-930a-6614053fc805.xml, MSiSCSI_QMIPSECStats structure [Storage Devices], *PMSiSCSI_QMIPSECStats, storage.msiscsi_qmipsecstats, PMSiSCSI_QMIPSECStats structure pointer [Storage Devices], _MSiSCSI_QMIPSECStats, iscsiprf/MSiSCSI_QMIPSECStats
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	iscsiprf.h
apiname:
-	MSiSCSI_QMIPSECStats
product: Windows
targetos: Windows
req.typenames: "*PMSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats"
---

# _MSiSCSI_QMIPSECStats structure


## -description


The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA. 


## -syntax


````
typedef struct _MSiSCSI_QMIPSECStats {
  ULONGLONG ActiveSA;
  ULONGLONG PendingKeyOperations;
  ULONGLONG KeyAdditions;
  ULONGLONG KeyDeletions;
  ULONGLONG ReKeys;
  ULONGLONG ActiveTunnels;
  ULONGLONG BadSPIPackets;
  ULONGLONG PacketsNotDecrypted;
  ULONGLONG PacketsNotAuthenticated;
  ULONGLONG PacketsWithReplayDetection;
  ULONGLONG ConfidentialBytesSent;
  ULONGLONG ConfidentialBytesReceived;
  ULONGLONG AuthenticatedBytesSent;
  ULONGLONG AuthenticatedBytesReceived;
  ULONGLONG TransportBytesSent;
  ULONGLONG TransportBytesReceived;
  ULONGLONG TunnelBytesSent;
  ULONGLONG TunnelBytesReceived;
} MSiSCSI_QMIPSECStats, *PMSiSCSI_QMIPSECStats;
````


## -struct-fields




#### - ActiveSA

The number of active IPsec security associations (SAs). 


#### - PendingKeyOperations

The number of IPsec key operations that are in progress. 


#### - KeyAdditions

The number of successful IPsec SA negotiations. 


#### - KeyDeletions

The number of IPsec SA key deletions. 


#### - ReKeys

The number of re-key operations for IPsec SAs. 


#### - ActiveTunnels

The number of active IPsec tunnels. 


#### - BadSPIPackets

The number of packets for which the security parameters index (SPI) was incorrect.


#### - PacketsNotDecrypted

The number of failed decryption packets. 


#### - PacketsNotAuthenticated

The number of packets for which data could not be verified.


#### - PacketsWithReplayDetection

The number of packets that contained a valid sequence number field.


#### - ConfidentialBytesSent

The number of bytes that are sent by using the encapsulating security payload (ESP) protocol.


#### - ConfidentialBytesReceived

The number of bytes that are received by using the ESP protocol.


#### - AuthenticatedBytesSent

The number of bytes that are sent by using the authentication header (AH) protocol.


#### - AuthenticatedBytesReceived

The number of bytes that are received by using the AH protocol.


#### - TransportBytesSent

The number of bytes that are sent by using the IPsec protocol. 


#### - TransportBytesReceived

The number of bytes that are received by using the IPsec protocol. 


#### - TunnelBytesSent

The number of bytes that are sent by using the IPsec tunnel mode.


#### - TunnelBytesReceived

The number of bytes that are received by using the IPsec tunnel mode.


## -remarks


It is optional that you implement this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563105">MSiSCSI_QMIPSECStats WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_QMIPSECStats structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

