---
UID: NS:dispmprt._DXGKARG_DPSBMTRANSMISSION
title: DXGKARG_DPSBMTRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKARG_DPSBMTRANSMISSION structure is a parameter for the DXGKDDI_DPSBMTRANSMISSION callback.
tech.root: display
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_DPSBMTRANSMISSION, *PDXGKARG_DPSBMTRANSMISSION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_DPSBMTRANSMISSION
 - DXGKARG_DPSBMTRANSMISSION
f1_keywords:
 - _DXGKARG_DPSBMTRANSMISSION
 - dispmprt/_DXGKARG_DPSBMTRANSMISSION
 - PDXGKARG_DPSBMTRANSMISSION
 - dispmprt/PDXGKARG_DPSBMTRANSMISSION
 - DXGKARG_DPSBMTRANSMISSION
 - dispmprt/DXGKARG_DPSBMTRANSMISSION
dev_langs:
 - c++
---

# DXGKARG_DPSBMTRANSMISSION structure


## -description

The **DXGKARG_DPSBMTRANSMISSION** structure is a parameter for the [**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md) callback.

## -struct-fields

### -field CanUseCachedData

When set, indicates that the driver can return a cached data reply. This data must be in Sideband Message (SBM) packet format.

### -field Reserved

Reserved; do not use.

### -field RootPortIndex

Index value of the DisplayPort-capable connector on which to perform the read or write operation. The driver returned the total number of DP-capable connectors on the GUP in a prior call to [**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md). Subsequent calls to [**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md) refer to the DP connectors with **RootPortIndex** ranging from **0** to **NumRootPorts - 1**.

### -field BufferSizeSupplied

Size, in bytes, of the buffer provided in **Data**.

### -field RequestLength

Size in bytes of **Data** in SBM packet size that the driver can directly write into DPCD range for DOWN_REQ.

### -field MaxReplyLength

Maximum size, in bytes, that **Data** is large enough for receiving a reply. The driver needs to discard overflowing packet.

### -field DPNativeError

Field in which the driver can encode more details about the error when returning STATUS_DEVICE_PROTOCOL_ERROR from [**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md).

### -field ActualReplyLength

Length of the actual reply returned by the driver, in bytes.

### -field Data

Buffer containing the data to write for a write operation, or in which to receive the data for a read operation.

## -remarks

## -see-also

[**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md)

[**DXGKDDI_DPSBMTRANSMISSION**](nc-dispmprt-dxgkddi_dpsbmtransmission.md)

