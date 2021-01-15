---
UID: NS:dispmprt._DXGKARG_DPI2CIOTRANSMISSION
title: DXGKARG_DPI2CIOTRANSMISSION
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: The DXGKARG_DPI2CIOTRANSMISSION structure is a parameter for the DXGKDDI_DPI2CIOTRANSMISSION callback.
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
req.typenames: DXGKARG_DPI2CIOTRANSMISSION, *PDXGKARG_DPI2CIOTRANSMISSION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_DPI2CIOTRANSMISSION
 - PDXGKARG_DPI2CIOTRANSMISSION
 - DXGKARG_DPI2CIOTRANSMISSION
f1_keywords:
 - _DXGKARG_DPI2CIOTRANSMISSION
 - dispmprt/_DXGKARG_DPI2CIOTRANSMISSION
 - PDXGKARG_DPI2CIOTRANSMISSION
 - dispmprt/PDXGKARG_DPI2CIOTRANSMISSION
 - DXGKARG_DPI2CIOTRANSMISSION
 - dispmprt/DXGKARG_DPI2CIOTRANSMISSION
dev_langs:
 - c++
---

# DXGKARG_DPI2CIOTRANSMISSION structure


## -description

The **DXGKARG_DPI2CIOTRANSMISSION** structure is a parameter for the [**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md) callback.

## -struct-fields

### -field Read

If set, perform a DP I2C over AUX read operation.

### -field Write

If set, perform a DP I2C over AUX write operation.

### -field EDDCMode

If set, the device at **I2CAddress** is Enhanced Display Data Channel (E-DDC).

### -field OffsetSizeInBytes

Offset size from **Offset**, in bytes, at which to write data for non-E-DDC devices.

### -field CanUseCachedData

If set, the driver can use cached data.

### -field Reserved

Reserved; do not use.

### -field RootPortIndex

Index value of the DP-capable connector on which to perform the DP I2C over AUX read or write operation. The driver returned the total number of DP-capable connectors on the GPU in a prior call to [**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md). Subsequent calls to [**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md) refer to the DP connectors with **RootPortIndex** ranging from **0** to **NumRootPorts - 1**.

### -field I2CAddress

I2C address. Set to 0xA0 for EDID, or 0xA4 for DisplayID.

### -field WordOffset

Word offset, in bytes.

### -field SegmentPointer

When **EDDCMode** is set, the driver should write **SegmentPointer** to I2C address 0x60. **SegmentPointer** identifies the 256-byte data block being accessed for E-DDC devices.

### -field Reserved1

Reserved; do not use.

### -field Offset

Address for IO within the device.

### -field BufferSizeSupplied

Size of the **Data** buffer, in bytes. **BufferSizeSupplied** should be greater than or equal to the larger of **BytesToWrite** and **BytesToWrite**.

### -field BytesToWrite

Number of bytes to write for a write operation.

### -field BytesToRead

Number of bytes to read for a read operation.

### -field DPNativeError

Field in which the driver can encode more details about the error when returning STATUS_DEVICE_PROTOCOL_ERROR from [**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md).

### -field BytesWritten

Number of bytes written. The driver should return this value as accurately as possible in the case of failure.

### -field BytesRead

Number of bytes read. The driver should return this value as accurately as possible in the case of failure.

### -field Data

Buffer containing the data to write for a write operation, and/or in which to receive the data for a read operation.

## -remarks

When **EDDCMode** is set, the driver should write **WordOffset** to **OffsetSizeInBytes**.

When **EDDCMode** is set, there are E-DDC devices at **I2CAddress** (0xA0 for EDID, 0xA4 for DisplayID). In this situation, the driver should write **SegmentPointer** to I2C address 0x60, **WordOffset** to **I2CAddress**,  and then carry out the IO operation. For all other I2C devices, the driver should write bytes of **Offset** according to **OffsetSizeInBytes**.

In case of failure, the driver should return **BytesWritten** and **BytesRead** as accurately as possible.

For Windows 10 version 2004, a write operation is only allowed for MCCS I2C address of 0x6E. All other operations will be blocked until a later OS release when access control is added.

## -see-also

[**DXGKDDI_DPI2CIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpi2ciotransmission.md)

[**DXGKDDI_QUERYDPCAPS**](nc-dispmprt-dxgkddi_querydpcaps.md)

