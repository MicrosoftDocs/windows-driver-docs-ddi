---
UID: NC:dispmprt.DXGKDDI_DPSBMTRANSMISSION
title: DXGKDDI_DPSBMTRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKDDI_DPSBMTRANSMISSION callback is used to communicate with DisplayPort (DP) branch devices and sink devices behind branch devices.
tech.root: display
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DPSBMTRANSMISSION
f1_keywords:
 - dispmprt/DXGKDDI_DPSBMTRANSMISSION
 - ""
dev_langs:
 - c++
---

# DXGKDDI_DPSBMTRANSMISSION callback function

## -description

The **DXGKDDI_DPSBMTRANSMISSION** callback is used to communicate with DisplayPort (DP) branch devices and sink devices behind branch devices via the sideband channel.

## -parameters

### -param Context

Context pointer provided when querying the interface.

### -param pArgs

Pointer to a [**DXGKARG_DPSBMTRANSMISSION**](ns-dispmprt-dxgkarg_dpsbmtransmission.md) structure.

## -returns

**DXGKDDI_DPSBMTRANSMISSION** returns STATUS_SUCCESS if it succeeds; otherwise it returns an error code such as one of the following:

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_DRIVER_INTERNAL_ERROR | An internal software error occurred.|  
| STATUS_ACCESS_DENIED | The request is not supported. For Windows 10 version 2004, only Sideband Message requests listed in the **Remarks** section below are supported. |
| STATUS_BUFFER_TOO_SMALL | The buffer is too small for Sideband message reply or other operations. |
| STATUS_DEVICE_HARDWARE_ERROR | A hardware error occurred. |
| STATUS_DEVICE_POWERED_OFF | The device is powered off. |
| STATUS_DEVICE_NOT_CONNECTED | The device is not connected. |
| STATUS_DEVICE_PROTOCOL_ERROR | An error occurred at the DP AUX, I2C over AUX protocol level. The driver can use **DPNativeError** to encode more details about the error. |

## -remarks

For Windows 10 version 2004, a driver is only required to support the following query type of Sideband Message (SBM) requests:

* GET_MESSAGE_TRANSACTION_VERSION
* LINK_ADDRESS
* QUERY_PAYLOAD
* REMOTE_DPCD_READ
* REMOTE_I2C_READ
* QUERY_STREAM_ENCRYPTION_STATUS

The display kernel runtime blocks other SBM requests.

For a SBM Transaction, a request is written to and reply is read from fixed DPCD ranges per the DP spec (DOWN_REQ and UP_REP), so there is no address field.

**DXGKDDI_DPSBMTRANSMISSION** is “atomic”, so the driver should wait for and receive the reply of the SBM request before returning. The SBM request in **pArgs->Data** is fully packetized by the caller, so the driver can directly write the **RequestLength** of **Data** in SBM packet size sequentially into DPCD range for DOWN_REQ. The driver should receive the SBM reply packets directly into **Data** without processing/interpretation.

The driver should use the End_Of_Message bit in the SideBand_MSG_Header to decide if a full reply has been received but should avoid further processing. **Data** can hold a reply up to **MaxReplyLength** in bytes, so the driver needs to discard the overflowing packet. The driver should return the actual length of the reply in **ActualReplyLength**.

The driver doesn’t need to specifically check for a NAK reply, which is decoded by the caller just as an other ACK reply. For a NAK reply, driver should return STATUS_SUCCESS.

The **MaxReplyLength** is at least 48 bytes, which is the maximum Sideband Message packet size. This allows the raw message to be copied directly for a single packet reply. For a reply with multiple packets, **MaxReplyLength** is calculated based on a packet size of 16 bytes and longest Relative Address in the SBM header to lower the possibility of insufficient buffer.

The **CanUseCachedData** flag indicates that driver can return a cached reply data, but it needs to be in SBM packet format.

## -see-also

[**DXGKARG_DPSBMTRANSMISSION**](ns-dispmprt-dxgkarg_dpsbmtransmission.md)
