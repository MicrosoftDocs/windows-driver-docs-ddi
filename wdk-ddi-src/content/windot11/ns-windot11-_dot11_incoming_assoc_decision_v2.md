---
UID: NS:windot11._DOT11_INCOMING_ASSOC_DECISION_V2
title: "_DOT11_INCOMING_ASSOC_DECISION_V2"
author: windows-driver-content
description: Information for an incoming association request is included in a DOT11_INCOMING_ASSOC_DECISION_V2 structure. This structure is sent with an OID_DOT11_INCOMING_ASSOCIATION_DECISION request.
old-location: netvista\dot11_incoming_assoc_decision_v2.htm
old-project: netvista
ms.assetid: E2455BD2-E540-4B81-84D8-E88D740407ED
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PDOT11_INCOMING_ASSOC_DECISION_V2, ,, 1, 2, A, C, D, DOT11_INCOMING_ASSOC_DECISION_V2, DOT11_INCOMING_ASSOC_DECISION_V2 structure [Network Drivers Starting with Windows Vista], E, G, I, M, N, O, P, PDOT11_INCOMING_ASSOC_DECISION_V2, PDOT11_INCOMING_ASSOC_DECISION_V2 structure pointer [Network Drivers Starting with Windows Vista], S, T, V, _, _DOT11_INCOMING_ASSOC_DECISION_V2, netvista.dot11_incoming_assoc_decision_v2, windot11/DOT11_INCOMING_ASSOC_DECISION_V2, windot11/PDOT11_INCOMING_ASSOC_DECISION_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	Windot11.h
apiname:
-	DOT11_INCOMING_ASSOC_DECISION_V2
product: Windows
targetos: Windows
req.typenames: DOT11_INCOMING_ASSOC_DECISION_V2, *PDOT11_INCOMING_ASSOC_DECISION_V2
req.product: Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_DECISION_V2 structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>Information for an incoming association request is included in a <b>DOT11_INCOMING_ASSOC_DECISION_V2</b> structure. This structure is sent with an <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/hh406480">OID_DOT11_INCOMING_ASSOCIATION_DECISION</a> request.


## -syntax


````
typedef struct _DOT11_INCOMING_ASSOC_DECISION_V2 {
  NDIS_OBJECT_HEADER       Header;
  DOT11_MAC_ADDRESS        PeerMacAddr;
  BOOLEAN                  bAccept;
  USHORT                   usReasonCode;
  ULONG                    uAssocResponseIEsOffset;
  ULONG                    uAssocResponseIEsLength;
  DOT11_WFD_STATUS_CODE    WFDStatus;
} DOT11_INCOMING_ASSOC_DECISION_V2, *PDOT11_INCOMING_ASSOC_DECISION_V2;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>DOT11_INCOMING_ASSOC_DECISION_V2</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_ INCOMING_ASSOC_DECISION_REVISION_2</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_INCOMING_ASSOC_DECISION_REVISION_2</td>
</tr>
</table>
 


### -field PeerMacAddr

The address of the peer station for the 802.11 station connect attempt.


### -field bAccept

The incoming association acceptance. If TRUE, the driver accepts the request. Otherwise, the request is rejected.


### -field usReasonCode

If bAccept == TRUE, the reason code is included in the association response.


### -field uAssocResponseIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) that the miniport driver must include in the probe response packet. The probe response is sent to the peer station seeking the association. This offset is from the start of the buffer that contains this structure.


### -field uAssocResponseIEsLength

The length, in bytes, of the array of IEs provided at <b>uAssocResponseIEsOffset</b>.


### -field WFDStatus

The status code to include in the Peer-to-Peer (P2P) IE of the association response if <b>bAccept</b> is FALSE.


## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/hh406480">OID_DOT11_INCOMING_ASSOCIATION_DECISION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_INCOMING_ASSOC_DECISION_V2 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

