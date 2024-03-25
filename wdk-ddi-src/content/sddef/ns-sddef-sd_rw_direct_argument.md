---
UID: NS:sddef._SD_RW_DIRECT_ARGUMENT
tech.root: sd
title: SD_RW_DIRECT_ARGUMENT
ms.date: 10/18/2022
targetos: Windows
description: Learn more about the SD_RW_DIRECT_ARGUMENT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: sddef.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SD_RW_DIRECT_ARGUMENT, *PSD_RW_DIRECT_ARGUMENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sddef.h
api_name:
 - _SD_RW_DIRECT_ARGUMENT
 - PSD_RW_DIRECT_ARGUMENT
 - SD_RW_DIRECT_ARGUMENT
f1_keywords:
 - _SD_RW_DIRECT_ARGUMENT
 - sddef/_SD_RW_DIRECT_ARGUMENT
 - PSD_RW_DIRECT_ARGUMENT
 - sddef/PSD_RW_DIRECT_ARGUMENT
 - SD_RW_DIRECT_ARGUMENT
 - sddef/SD_RW_DIRECT_ARGUMENT
dev_langs:
 - c++
helpviewer_keywords:
 - _SD_RW_DIRECT_ARGUMENT
---

## -description

The SD_RW_DIRECT_ARGUMENT structure is used in conjunction with the [**SdBusSubmitRequest**](../ntddsd/nf-ntddsd-sdbussubmitrequest.md) routine or the [**SdBusSubmitRequestAsync**](../ntddsd/nf-ntddsd-sdbussubmitrequestasync.md) routine to send a Secure Digital (SD) read or write request to the bus driver.

## -struct-fields

### -field u

Name of union.

### -field u.bits

Structure that contains the following members.

### -field u.bits.Data

Contains eight bits of data to read or write.

### -field u.bits.Reserved1

Reserved.

### -field u.bits.Address

Indicates the address of the function space accessed by the operation.

### -field u.bits.Reserved2

Reserved.

### -field u.bits.ReadAfterWrite

Indicates that the operation should read the data at the specified location after writing to that location. The primary use of this option is to write to a control register and then read status information at the same address immediately afterwards. The caller must set **WriteToDevice** to 1 or this member will have no effect.

### -field u.bits.Function

Contains the number of the function on the I/O card whose data space is accessed by the operation. A value of 0 indicates that the operation should address the common I/O area, rather than the I/O space of a particular card function.

To retrieve a function number for an SD device, a device driver must do the following:

1. Set the **RequestFunction** member of [**SDBUS_REQUEST_PACKET**](/previous-versions/windows/hardware/device-stage/drivers/ff537931(v=vs.85)) to an [**SD_REQUEST_FUNCTION**](../ntddsd/ne-ntddsd-sd_request_function.md) enumerator value of SDRF_GET_PROPERTY.

1. Set the **Property** member of [**SDBUS_REQUEST_PACKET**](/previous-versions/windows/hardware/device-stage/drivers/ff537931(v=vs.85)) to SDP_FUNCTION_NUMBER.

1. Send the request to the bus driver by passing the initialized SDBUS_REQUEST_PACKET structure to either [**SdBusSubmitRequest**](../ntddsd/nf-ntddsd-sdbussubmitrequest.md) or [**SdBusSubmitRequestAsync**](../ntddsd/nf-ntddsd-sdbussubmitrequestasync.md).

### -field u.bits.WriteToDevice

Indicates a write operation when set to 1, and a read operation when set to 0.

### -field u.AsULONG

Contains all 32 bits of the data stored in the preceding members, represented as a ULONG.

## -see-also

[**SdBusSubmitRequest**](../ntddsd/nf-ntddsd-sdbussubmitrequest.md)

[**SdBusSubmitRequestAsync**](../ntddsd/nf-ntddsd-sdbussubmitrequestasync.md)
