---
UID: NE:wditypes._WDI_ASSOC_STATUS
title: "_WDI_ASSOC_STATUS"
author: windows-driver-content
description: The WDI_ASSOC_STATUS enumeration defines the association status values.
old-location: netvista\wdi_assoc_status.htm
old-project: netvista
ms.assetid: 8268031A-7493-4A42-9211-D02B8AA50F34
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, C, D, I, O, S, T, U, W, WDI_ASSOC_STATUS, WDI_ASSOC_STATUS enumeration [Device and Driver Installation], WDI_ASSOC_STATUS_ABORTED, WDI_ASSOC_STATUS_ASSOC_EXCHANGE_FAILURE, WDI_ASSOC_STATUS_ASSOC_FAILED_BY_PEER, WDI_ASSOC_STATUS_ASSOC_REQUEST_TX_NO_ACK, WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH, WDI_ASSOC_STATUS_AUTH_EXCHANGE_FAILURE, WDI_ASSOC_STATUS_AUTH_FAILED_BY_PEER, WDI_ASSOC_STATUS_AUTH_REQUEST_TX_NO_ACK, WDI_ASSOC_STATUS_AUTH_RESPONSE_CAPABILITY_MISMATCH, WDI_ASSOC_STATUS_BAD_ASSOC_RESPONSE, WDI_ASSOC_STATUS_BAD_AUTH_RESPONSE, WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED, WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST, WDI_ASSOC_STATUS_DISASSOCIATE_BY_DEVICE_RESET, WDI_ASSOC_STATUS_DISASSOCIATE_NEEDED_REASSOC, WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE, WDI_ASSOC_STATUS_DISASSOCIATE_UNABLE_TO_MAINTAIN, WDI_ASSOC_STATUS_FAILURE, WDI_ASSOC_STATUS_NO_ASSOC_RESPONSE, WDI_ASSOC_STATUS_NO_AUTH_RESPONSE, WDI_ASSOC_STATUS_NO_BEACON_PROBE_RESPONSE, WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED, WDI_ASSOC_STATUS_PEER_DISASSOCIATED, WDI_ASSOC_STATUS_PROBE_TX_FAILURE, WDI_ASSOC_STATUS_RADIO_OFF, WDI_ASSOC_STATUS_ROAMING_ASSOCIATION_LOST, WDI_ASSOC_STATUS_ROAMING_BETTER_AP_FOUND, WDI_ASSOC_STATUS_ROAMING_LOW_LINK_QUALITY, WDI_ASSOC_STATUS_SUCCESS, WDI_ASSOC_STATUS_UNREACHABLE, _, _WDI_ASSOC_STATUS, netvista.wdi_assoc_status, netvista.wifi_assoc_status, wditypes/WDI_ASSOC_STATUS, wditypes/WDI_ASSOC_STATUS_ABORTED, wditypes/WDI_ASSOC_STATUS_ASSOC_EXCHANGE_FAILURE, wditypes/WDI_ASSOC_STATUS_ASSOC_FAILED_BY_PEER, wditypes/WDI_ASSOC_STATUS_ASSOC_REQUEST_TX_NO_ACK, wditypes/WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH, wditypes/WDI_ASSOC_STATUS_AUTH_EXCHANGE_FAILURE, wditypes/WDI_ASSOC_STATUS_AUTH_FAILED_BY_PEER, wditypes/WDI_ASSOC_STATUS_AUTH_REQUEST_TX_NO_ACK, wditypes/WDI_ASSOC_STATUS_AUTH_RESPONSE_CAPABILITY_MISMATCH, wditypes/WDI_ASSOC_STATUS_BAD_ASSOC_RESPONSE, wditypes/WDI_ASSOC_STATUS_BAD_AUTH_RESPONSE, wditypes/WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED, wditypes/WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST, wditypes/WDI_ASSOC_STATUS_DISASSOCIATE_BY_DEVICE_RESET, wditypes/WDI_ASSOC_STATUS_DISASSOCIATE_NEEDED_REASSOC, wditypes/WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE, wditypes/WDI_ASSOC_STATUS_DISASSOCIATE_UNABLE_TO_MAINTAIN, wditypes/WDI_ASSOC_STATUS_FAILURE, wditypes/WDI_ASSOC_STATUS_NO_ASSOC_RESPONSE, wditypes/WDI_ASSOC_STATUS_NO_AUTH_RESPONSE, wditypes/WDI_ASSOC_STATUS_NO_BEACON_PROBE_RESPONSE, wditypes/WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED, wditypes/WDI_ASSOC_STATUS_PEER_DISASSOCIATED, wditypes/WDI_ASSOC_STATUS_PROBE_TX_FAILURE, wditypes/WDI_ASSOC_STATUS_RADIO_OFF, wditypes/WDI_ASSOC_STATUS_ROAMING_ASSOCIATION_LOST, wditypes/WDI_ASSOC_STATUS_ROAMING_BETTER_AP_FOUND, wditypes/WDI_ASSOC_STATUS_ROAMING_LOW_LINK_QUALITY, wditypes/WDI_ASSOC_STATUS_SUCCESS, wditypes/WDI_ASSOC_STATUS_UNREACHABLE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname:
-	WDI_ASSOC_STATUS
product: Windows
targetos: Windows
req.typenames: WDI_ASSOC_STATUS
req.product: Windows 10 or later.
---

# _WDI_ASSOC_STATUS enumeration


## -description


The WDI_ASSOC_STATUS enumeration defines the association status values.


## -syntax


````
typedef enum _WDI_ASSOC_STATUS { 
  WDI_ASSOC_STATUS_SUCCESS                             = 0,
  WDI_ASSOC_STATUS_FAILURE                             = 1,
  WDI_ASSOC_STATUS_UNREACHABLE                         = 2,
  WDI_ASSOC_STATUS_RADIO_OFF                           = 3,
  WDI_ASSOC_STATUS_ABORTED                             = 5,
  WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED            = 6,
  WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST               = 7,
  WDI_ASSOC_STATUS_ROAMING_BETTER_AP_FOUND             = 10,
  WDI_ASSOC_STATUS_ROAMING_ASSOCIATION_LOST            = 11,
  WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED                = 13,
  WDI_ASSOC_STATUS_PEER_DISASSOCIATED                  = 14,
  WDI_ASSOC_STATUS_ROAMING_LOW_LINK_QUALITY            = 15,
  WDI_ASSOC_STATUS_PROBE_TX_FAILURE                    = 30,
  WDI_ASSOC_STATUS_NO_BEACON_PROBE_RESPONSE            = 31,
  WDI_ASSOC_STATUS_AUTH_REQUEST_TX_NO_ACK              = 40,
  WDI_ASSOC_STATUS_NO_AUTH_RESPONSE                    = 41,
  WDI_ASSOC_STATUS_AUTH_RESPONSE_CAPABILITY_MISMATCH   = 42,
  WDI_ASSOC_STATUS_BAD_AUTH_RESPONSE                   = 43,
  WDI_ASSOC_STATUS_AUTH_FAILED_BY_PEER                 = 44,
  WDI_ASSOC_STATUS_AUTH_EXCHANGE_FAILURE               = 45,
  WDI_ASSOC_STATUS_ASSOC_REQUEST_TX_NO_ACK             = 50,
  WDI_ASSOC_STATUS_NO_ASSOC_RESPONSE                   = 51,
  WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH  = 52,
  WDI_ASSOC_STATUS_BAD_ASSOC_RESPONSE                  = 53,
  WDI_ASSOC_STATUS_ASSOC_FAILED_BY_PEER                = 54,
  WDI_ASSOC_STATUS_ASSOC_EXCHANGE_FAILURE              = 55,
  WDI_ASSOC_STATUS_DISASSOCIATE_BY_DEVICE_RESET        = 60,
  WDI_ASSOC_STATUS_DISASSOCIATE_UNABLE_TO_MAINTAIN     = 61,
  WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE            = 62,
  WDI_ASSOC_STATUS_DISASSOCIATE_NEEDED_REASSOC         = 63
} WDI_ASSOC_STATUS;
````


## -enum-fields




### -field WDI_ASSOC_STATUS_SUCCESS

The operation completed successfully.


### -field WDI_ASSOC_STATUS_FAILURE

The operation completed with a failure and none of the other status codes apply.


### -field WDI_ASSOC_STATUS_UNREACHABLE

The operation failed because the peer is unreachable. The detection of an unreachable peer is up to the port. For example, a peer can be considered unreachable if the port does not receive responses to management requests such as probe requests or association requests. If the device has more specific information, it should use one of the more specific reason codes.


### -field WDI_ASSOC_STATUS_RADIO_OFF

The operation failed because the radio is off. This can be used if the hardware radio switch is turned off.


### -field WDI_ASSOC_STATUS_PHY_DISABLED


### -field WDI_ASSOC_STATUS_ABORTED

The operation was cancelled due to a request from the host. If the request from the host was for disassociation, WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST should be used.


### -field WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED

The connect or roaming operation failed because the post could not successfully associate.


### -field WDI_ASSOC_STATUS_PROBE_TX_FAILURE

The association failed because the port was not able to successfully send a 802.11 probe request to the peer.


### -field WDI_ASSOC_STATUS_NO_BEACON_PROBE_RESPONSE

The association failed because no beacon or probe response was received from the peer.


### -field WDI_ASSOC_STATUS_AUTH_REQUEST_NO_ACK


### -field WDI_ASSOC_STATUS_NO_AUTH_RESPONSE

The association failed because an 802.11 authentication response frame was not received after a successful send of an 802.11 authentication request.


### -field WDI_ASSOC_STATUS_AUTH_RESPONSE_CAPABILITY_MISMATCH

The association failed because an 802.11 authentication response was received with a status of success, but was rejected due to capability mismatch.


### -field WDI_ASSOC_STATUS_BAD_AUTH_RESPONSE

The association failed because an 802.11 authentication response was received with a status of success, but was rejected due to a reason other than capability mismatch (for example, because of invalid content).


### -field WDI_ASSOC_STATUS_AUTH_FAILED_BY_PEER

The association failed because the peer failed the 802.11 authentication with a failure reason. The authentication response frame must be included in the indication.


### -field WDI_ASSOC_STATUS_AUTH_EXCHANGE_FAILURE

The association failed because the 802.11 authentication did not finish successfully. This reason should only be used if the port is not able to use one of the specific 802.11 authentication exchange failure codes.


### -field WDI_ASSOC_STATUS_ASSOC_REQUEST_NO_ACK


### -field WDI_ASSOC_STATUS_NO_ASSOC_RESPONSE

The association failed because an 802.11 association response frame was not received after a successful send of an 802.11 association request.


### -field WDI_ASSOC_STATUS_ASSOC_RESPONSE_CAPABILITY_MISMATCH

The association failed because an 802.11 association response was received with a status of success, but was rejected due to capability mismatch. The association response frame should be included in the indication.


### -field WDI_ASSOC_STATUS_BAD_ASSOC_RESPONSE

The association failed because an 802.11 association response was received with a status of success, but was rejected due to a reason other than capability mismatch (for example, because of invalid content). The association response frame should be included in the indication.


### -field WDI_ASSOC_STATUS_ASSOC_FAILED_BY_PEER

The association failed because the peer failed the 802.11 association request with a failure reason. The association response frame should be included in the indication.


### -field WDI_ASSOC_STATUS_ASSOC_EXCHANGE_FAILURE

The association failed because the 802.11 association did not finish successfully. This reason should only be used if the port is not able to use one of the specific 802.11 association exchange failure codes.


### -field WDI_ASSOC_STATUS_DISASSOCIATED_BY_HOST

The host requested that the port disassociate.


### -field WDI_ASSOC_STATUS_DISASSOCIATE_BY_DEVICE_RESET

The disassociation is  because the device was reset (for example, due to a hang, NdisReset, or a reset that the miniport did internally).


### -field WDI_ASSOC_STATUS_DISASSOCIATE_UNABLE_TO_MAINTAIN

The disassociation is because the port is unable to maintain the connection due to other operations being performed on the port (for example, Bluetooth coexistence reasons). This should only be used if the port is not able to use one of the specific failure codes.


### -field WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE

The operation failed because the peer is not being heard from. The detection of an unreachable peer is up to the port. For example, a peer can be considered unreachable if the port misses multiple beacons from the peer.


### -field WDI_ASSOC_STATUS_DISASSOCIATE_NEEDED_REASSOC

The disassociation is because the port believes it needs to reassociate to the peer. This may be because the port determines that the peer thinks the association is no longer valid. This should only be used if the port is not able to use one of the specific failure codes (for example, WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED).


### -field WDI_ASSOC_STATUS_PEER_DEAUTHENTICATED

The port received a deauthentication frame from the peer. The deauthentication frame must be included in the indication.


### -field WDI_ASSOC_STATUS_PEER_DISASSOCIATED

The port received a disassociation frame from the peer. The disassociation frame must be included in the indication.


### -field WDI_ASSOC_STATUS_ROAMING_BETTER_AP_FOUND

The connection was torn down because a better access point was found.


### -field WDI_ASSOC_STATUS_ROAMING_ASSOCIATION_LOST

The port lost the link with the peer. If device has more specific information, it should use one of the more specific reason codes such as WDI_ASSOC_STATUS_DISASSOCIATE_NOT_VISIBLE.


### -field WDI_ASSOC_STATUS_ROAMING_LOW_LINK_QUALITY

The link quality to the peer is low.


### -field WDI_ASSOC_STATUS_RESERVED_0




#### - WDI_ASSOC_STATUS_AUTH_REQUEST_TX_NO_ACK

The association failed because the port was unable to get an ACK for the 802.11 authentication request frame.


#### - WDI_ASSOC_STATUS_ASSOC_REQUEST_TX_NO_ACK

The association failed because port was unable to get an ACK for the 802.11 association request frame.

