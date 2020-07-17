---
UID: NS:dispmprt._DXGKARG_DPAUXIOTRANSMISSION
title: DXGKARG_DPAUXIOTRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKARG_DPAUXIOTRANSMISSION structure is a parameter for the DXGKDDI_DPAUXIOTRANSMISSION callback.
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
req.typenames: DXGKARG_DPAUXIOTRANSMISSION, *PDXGKARG_DPAUXIOTRANSMISSION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_DPAUXIOTRANSMISSION
 - DXGKARG_DPAUXIOTRANSMISSION
f1_keywords:
 - dispmprt/_DXGKARG_DPAUXIOTRANSMISSION
 - dispmprt/DXGKARG_DPAUXIOTRANSMISSION
 - ""
dev_langs:
 - c++
---

# DXGKARG_DPAUXIOTRANSMISSION structure

## -description

The **DXGKARG_DPAUXIOTRANSMISSION** structure is a parameter for the [**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md) callback.

## -struct-fields

### -field Write

Indicates whether the operation is read or write. A value of zero indicates that the DisplayPort Configuration Data (DPCD) operation is a read; a value of one indicates a write to the DPCD.

### -field CanUseCachedData

When set, indicates that the driver can use cached data without actual AUX transaction.

### -field Reserved

Reserved; do not use.

### -field RootPortIndex

Index value of the DP-capable connector on which to perform the DPCD read or write operation. The driver returned the total number of DP-capable connectors on the GPU in a prior call to [DXGKDDI_QUERYDPCAPS](nc-dispmprt-dxgkddi_querydpcaps.md). Subsequent calls to [**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md) refer to the DP connectors with **RootPortIndex** ranging from **0** to **NumRootPorts - 1**.

### -field DPCDAddress

The DPCD address for the read or write operation.

### -field NumBytesRequested

Number of bytes to read/write starting at **DPCDAddress**.

### -field DPNativeError

Field in which the driver can encode more details about the error when returning STATUS_DEVICE_PROTOCOL_ERROR from [**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md).  

### -field NumBytesDone

Actual number of bytes that were read or written.

### -field Data

Buffer containing the data to write for a write operation, or in which to receive the data for a read operation.

## -remarks

## -see-also

[DXGKDDI_QUERYDPCAPS](nc-dispmprt-dxgkddi_querydpcaps.md)

[**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md)
