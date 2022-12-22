---
UID: NF:ndis.NdisMIndicateStatus
tech.root: 
title: NdisMIndicateStatus
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: 
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisMIndicateStatus
f1_keywords:
 - NdisMIndicateStatus
 - ndis/NdisMIndicateStatus
dev_langs:
 - c++
helpviewer_keywords:
 - NdisMIndicateStatus
---

# NdisMIndicateStatus function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisMIndicateStatus** indicates changes in the status of a NIC to higher-level NDIS drivers.

## -parameters

### -param MiniportHandle [in]

Specifies the handle originally input to [**MiniportInitialize**](ff550472\(v=vs.85\).md).

### -param GeneralStatus [in]

Specifies the NDIS\_STATUS\_ *XXX* value that indicates the general change in status for the NIC.

### -param StatusBuffer [in]

Pointer to a caller-allocated buffer containing data that is medium-specific and dependent on the value of *GeneralStatus*. It indicates detailed information about the change in status.

### -param StatusBufferSize [in]

Specifies the size in bytes of the buffer at *StatusBuffer*.

## -remarks

When a miniport driver calls **NdisMIndicateStatus**, NDIS calls each bound protocol's [**ProtocolStatus**](ff563257\(v=vs.85\).md) function. This allows a bound protocol driver or, possibly, the configuration manager to log the change in status of an underlying NIC or to take corrective action. For example, a protocol might call [**NdisReset**](ff554691\(v=vs.85\).md), depending on the NDIS\_STATUS\_ *XXX* indicated.

When a miniport driver calls **NdisMIndicateStatus** to report a change in NIC status, NDIS can call the [*MiniportReset*](ff550502\(v=vs.85\).md) function to try restoring the NIC to a working condition. In these circumstances, NDIS can call bound protocols only with NDIS\_STATUS\_RESET\_START and later with NDIS\_STATUS\_RESET\_END, rather than with the *GeneralStatus* indicated by the miniport driver.

**NdisMIndicateStatus** provides two pieces of information:

- An overall status value indicating the general change in status.
- A specific reason for the general change, which can be network-specific. For example, ring-insertion failures are particular to Token Ring (802.5) networks, but are irrelevant to Ethernet (802.3) NICs and their drivers.

A miniport driver also can call **NdisMIndicateStatus** to indicate problems such as cables that have been accidentally removed and then reinserted or a ring that has temporarily failed. For example, suppose both the following conditions occur:

- The miniport driver calls **NdisMIndicateStatus** with NDIS\_STATUS\_RING\_STATUS.
- The *StatusBuffer* contains one of the following status values:

  - NDIS\_RING\_LOBE\_WIRE\_FAULT
  - NDIS\_RING\_HARD\_ERROR
   NDIS\_RING\_SIGNAL\_LOSS

After such a change in status has been signaled with an indication, any associated thresholds or statistics counters remain unchanged.

A miniport driver cannot call **NdisMIndicateStatus** in the context of its [**MiniportISR**](ff550478\(v=vs.85\).md), [**MiniportHalt**](ff549451\(v=vs.85\).md), or [**MiniportShutdown**](ff550533\(v=vs.85\).md) function. Only a deserialized miniport driver can call **NdisMIndicateStatus** in the context of its [**MiniportInitialize**](ff550472\(v=vs.85\).md) function.

A miniport driver must release any spin lock that it is holding before calling **NdisMIndicateStatus**.

Serialized callers of **NdisMIndicateStatus** must run at IRQL = DISPATCH\_LEVEL. Deserialized callers of **NdisMIndicateStatus** must run at IRQL \<= DISPATCH\_LEVEL.

**Indicating the Loss and Restoration of a Network Connection**

When a miniport driver senses that the network connection has been lost, it should call **NdisMIndicateStatus** with NDIS\_STATUS\_MEDIA\_DISCONNECT. When the connection is restored, the miniport driver should call **NdisMIndicateStatus** with NDIS\_STATUS\_MEDIA\_CONNECT.

**Note**   802.11 miniport drivers must follow the media status guidelines for wireless LANs when generating network connection indications. For more information about these guidelines, see [Media Status Indications for 802.11 Networks](ff549301\(v=vs.85\).md).

**802.11 Wireless LAN Miniport Driver Calls to NdisMIndicateStatus**

802.11 wireless LAN (WLAN) miniport drivers can make various indications specific to the WLAN media. For example, the miniport driver can make a WLAN-specific indication when the following occur:

- The driver detects that the received signal strength of its current BSS association has changed.
- The driver detects a TKIP MIC failure on a received packet.

The following types of WLAN-specific indications can be made by 802.11 miniport drivers with **NdisMIndicateStatus**:

- [RSSI Indications](ff564096\(v=vs.85\).md)
- [Authentication Indications](ff544134\(v=vs.85\).md)
- [PMKID Candidate List Indications](ff562383\(v=vs.85\).md)
- [Media Streaming Indications](ff549317\(v=vs.85\).md)
- [Radio State Indications](ff563284\(v=vs.85\).md)

For more information about these media specific indications, see [802.11 Media-Specific Status Indications](ff543911\(v=vs.85\).md).

**WAN Miniport Driver Calls to NdisMIndicateStatus**

Most WAN NIC drivers indicate status with some special status codes and buffer contents. These status indications are generated by WAN NIC drivers, and NDIS protocol drivers bound to such a miniport driver can ignore these indications. However, processing these indications correctly usually results in improved performance for protocols and for WAN NIC drivers.

The following four types of WAN-specific indications can be sent to bound protocol drivers with **NdisMIndicateStatus**:

- Line up
- Line down
- Fragment
- TAPI line event

**NDIS\_STATUS\_WAN\_LINE\_UP**

A WAN miniport driver makes a line-up indication whenever a new link becomes active. Until this occurs, the NIC will accept frames and let them succeed or fail, but it is unlikely that they will actually be received by any remote node. Until this occurs, protocols should reduce their timers and retry counts to quickly fail any outgoing connection attempts.

The WAN miniport driver makes this indication with **NdisMIndicateStatus** before it returns from the [OID\_TAPI\_GET\_ID](ff561166\(v=vs.85\).md) request.

The status code for the line-up indication is NDIS\_STATUS\_WAN\_LINE\_UP. The buffer at *StatusBuffer* is formatted as an [**NDIS\_MAC\_LINE\_UP**](ff557058\(v=vs.85\).md) structure.

**NDIS\_STATUS\_WAN\_LINE\_DOWN**

A WAN miniport driver makes a line-down indication whenever a link goes down. When this occurs, bound protocols should reduce their timers and retry counts until the next line-up indication.

The status code for the line-down indication is NDIS\_STATUS\_WAN\_LINE\_DOWN. The buffer at *StatusBuffer* is formatted as an [**NDIS\_MAC\_LINE\_DOWN**](ff557057\(v=vs.85\).md) structure.

**NDIS\_STATUS\_WAN\_FRAGMENT**

A WAN miniport driver makes a fragment indication whenever it receives a partial packet from the remote node. When this occurs, a bound protocol should send frames to the remote node that will notify it of this situation, rather than waiting for a time-out to occur.

The status code for the fragment indication is NDIS\_STATUS\_WAN\_FRAGMENT. The buffer at *StatusBuffer* is formatted as an [**NDIS\_MAC\_FRAGMENT**](ff557055\(v=vs.85\).md) structure.

NDISWAN monitors dropped packets by counting the number of fragment indications on each link.

**NDIS\_TAPI\_EVENT**

A WAN miniport driver must use a *GeneralStatus* value of NDIS\_STATUS\_TAPI\_INDICATION for TAPI status indications *.* The buffer at *StatusBuffer* is formatted as an NDIS\_TAPI\_EVENT structure.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff563600"><strong>NdisMIndicateStatusEx</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.

## -see-also

- [**MiniportInitialize**](ff550472\(v=vs.85\).md)
- [*MiniportReset*](ff550502\(v=vs.85\).md)
- [**NDIS\_MAC\_FRAGMENT**](ff557055\(v=vs.85\).md)
- [**NDIS\_MAC\_LINE\_DOWN**](ff557057\(v=vs.85\).md)
- [**NDIS\_MAC\_LINE\_UP**](ff557058\(v=vs.85\).md)
- [**NdisMIndicateStatusComplete**](ff553540\(v=vs.85\).md)
- [**NDIS\_TAPI\_EVENT**](ff558986\(v=vs.85\).md)
- [**ProtocolStatus**](ff563257\(v=vs.85\).md)
- [Media Status Indications for 802.11 Networks](ff549301\(v=vs.85\).md)
- [802.11 Media-Specific Status Indications](ff543911\(v=vs.85\).md)
