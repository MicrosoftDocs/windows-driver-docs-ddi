---
UID: NS:iscsiprf._MSiSCSI_MMIPSECStats
title: "_MSiSCSI_MMIPSECStats"
author: windows-driver-content
description: The MSiSCSI_MMIPSECStats structure is used to report main mode IPsec statistics.
old-location: storage\msiscsi_mmipsecstats.htm
old-project: storage
ms.assetid: 75b11689-f940-467e-92ee-59b5e0adbf70
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMSiSCSI_MMIPSECStats, MSiSCSI_MMIPSECStats, MSiSCSI_MMIPSECStats structure [Storage Devices], PMSiSCSI_MMIPSECStats, PMSiSCSI_MMIPSECStats structure pointer [Storage Devices], _MSiSCSI_MMIPSECStats, iscsiprf/MSiSCSI_MMIPSECStats, iscsiprf/PMSiSCSI_MMIPSECStats, storage.msiscsi_mmipsecstats, structs-iSCSI_6edce57f-fce5-422a-a98f-049cc6418514.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiprf.h
api_name:
-	MSiSCSI_MMIPSECStats
product: Windows
targetos: Windows
req.typenames: MSiSCSI_MMIPSECStats, *PMSiSCSI_MMIPSECStats
---

# _MSiSCSI_MMIPSECStats structure


## -description


The MSiSCSI_MMIPSECStats structure is used to report main mode IPsec statistics. 


## -struct-fields




### -field ActiveAcquire

The number of active require requests that the IPsec driver has sent to the Internet Key Exchange (IKE) service. Typically, the number of active acquire requests is 1. Under a heavy load, the number of active acquire requests is 1 plus the number of requests that are waiting in the queue of the IKE service. 


### -field ActiveReceive

The number of IKE messages (that is, active receive requests) that are queued for processing.


### -field AcquireFailures

The number of active acquire requests that have failed.


### -field ReceiveFailures

The number of failures that have occurred while drivers in the TCP stack are receiving IKE messages.


### -field SendFailures

The number of failures that have occurred while drivers in the TCP stack are sending IKE messages.


### -field AcquireHeapSize

The number of IKE messages that the acquire heap can hold. This number increases under a heavy load and then gradually decreases over time, as the acquire heap is emptied.


### -field ReceiveHeapSize

The number of incoming IKE messages that the IKE receive buffers can hold.


### -field NegotiationFailures

The total number of negotiation failures that occurred during main mode (also known as <i>phase 1</i>) negotiation or during quick mode (also known as <i>phase 2</i>) negotiation.


### -field AuthenticationFailures

The number of identity authentication failures that occurred during main mode negotiation. This number includes kerberos failures, certificate failures, and preshared key failures.


### -field InvalidCookiesReceived

The number of invalid cookies that the initiator has received in IKE messages. Cookies are invalid if the cookie state does not correspond to the state of an active main mode security association (SA).


### -field TotalGetSPI

The number of requests that the IKE service submitted to obtain a unique security parameters index (SPI).


### -field KeyAdditions

The number of outbound quick mode SAs that the IKE service has added.


### -field KeyUpdates

The number of inbound quick mode SAs that the IKE service has added.


### -field GetSPIFailures

The total number of unsuccessful attempts that the IKE service has made to obtain a unique SPI. 


### -field KeyAdditionFailures

The number of outbound quick-mode SAs that the IKE service has submitted unsuccessfully.


### -field KeyUpdateFailures

The number of inbound quick-mode SAs that the IKE service has added.


### -field ConnectionListSize

The number of quick-mode state entries.


### -field OakleyMainMode

The number of successful SAs that are created during main mode negotiations.


### -field OakleyQuickMode

The number of successful SAs that are created during quick-mode negotiations.


### -field InvalidPackets

The number of received IKE messages that are invalid, including IKE messages with invalid header fields, incorrect payload lengths, or incorrect (nonzero) responder cookies that should be 0.


### -field SoftAssociations

The number of negotiations that resulted in the use of plaintext SAs (also known as <i>soft SAs</i>). This value typically reflects the number of associations that the initiator established with computers that did not respond to main mode negotiation attempts. Computers that do not respond might not support IPSec, or they might support IPSec but not have an IPSec policy with which to negotiate security with an IPSec peer.


## -remarks



It is optional that you implement this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563077">MSiSCSI_MMIPSECStats WMI Class</a>
 

 

