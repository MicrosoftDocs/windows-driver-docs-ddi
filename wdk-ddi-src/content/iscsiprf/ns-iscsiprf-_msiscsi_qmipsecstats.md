---
UID: NS:iscsiprf._MSiSCSI_QMIPSECStats
title: _MSiSCSI_QMIPSECStats (iscsiprf.h)
description: The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA.
old-location: storage\msiscsi_qmipsecstats.htm
tech.root: storage
ms.assetid: 265ed956-1065-44be-ac8e-94bab2e4e8b8
ms.date: 03/29/2018
keywords: ["_MSiSCSI_QMIPSECStats structure"]
ms.keywords: "*PMSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats, MSiSCSI_QMIPSECStats structure [Storage Devices], PMSiSCSI_QMIPSECStats, PMSiSCSI_QMIPSECStats structure pointer [Storage Devices], _MSiSCSI_QMIPSECStats, iscsiprf/MSiSCSI_QMIPSECStats, iscsiprf/PMSiSCSI_QMIPSECStats, storage.msiscsi_qmipsecstats, structs-iSCSI_979ce8ac-35be-4ac1-930a-6614053fc805.xml"
f1_keywords:
 - "iscsiprf/MSiSCSI_QMIPSECStats"
 - "MSiSCSI_QMIPSECStats"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiprf.h
api_name:
- MSiSCSI_QMIPSECStats
targetos: Windows
req.typenames: MSiSCSI_QMIPSECStats, *PMSiSCSI_QMIPSECStats
---

# _MSiSCSI_QMIPSECStats structure


## -description


The MSiSCSI_QMIPSECStats structure can be used by an iSCSI initiator to report IPsec statistics for an HBA. 


## -struct-fields




### -field ActiveSA

The number of active IPsec security associations (SAs). 


### -field PendingKeyOperations

The number of IPsec key operations that are in progress. 


### -field KeyAdditions

The number of successful IPsec SA negotiations. 


### -field KeyDeletions

The number of IPsec SA key deletions. 


### -field ReKeys

The number of re-key operations for IPsec SAs. 


### -field ActiveTunnels

The number of active IPsec tunnels. 


### -field BadSPIPackets

The number of packets for which the security parameters index (SPI) was incorrect.


### -field PacketsNotDecrypted

The number of failed decryption packets. 


### -field PacketsNotAuthenticated

The number of packets for which data could not be verified.


### -field PacketsWithReplayDetection

The number of packets that contained a valid sequence number field.


### -field ConfidentialBytesSent

The number of bytes that are sent by using the encapsulating security payload (ESP) protocol.


### -field ConfidentialBytesReceived

The number of bytes that are received by using the ESP protocol.


### -field AuthenticatedBytesSent

The number of bytes that are sent by using the authentication header (AH) protocol.


### -field AuthenticatedBytesReceived

The number of bytes that are received by using the AH protocol.


### -field TransportBytesSent

The number of bytes that are sent by using the IPsec protocol. 


### -field TransportBytesReceived

The number of bytes that are received by using the IPsec protocol. 


### -field TunnelBytesSent

The number of bytes that are sent by using the IPsec tunnel mode.


### -field TunnelBytesReceived

The number of bytes that are received by using the IPsec tunnel mode.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-qmipsecstats-wmi-class">MSiSCSI_QMIPSECStats WMI Class</a>
 

 

