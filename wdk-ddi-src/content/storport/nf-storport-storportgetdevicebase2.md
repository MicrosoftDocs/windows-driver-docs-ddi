---
UID: NF:storport.StorPortGetDeviceBase2
tech.root: storage
title: StorPortGetDeviceBase2
ms.date: 03/19/2024
targetos: Windows
description: The StorPortGetDeviceBase2 function is like StorPortGetDeviceBase, but the Flags parameter allows for additional optional behavior.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
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
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetDeviceBase2
f1_keywords:
 - StorPortGetDeviceBase2
 - storport/StorPortGetDeviceBase2
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortGetDeviceBase2
---

# StorPortGetDeviceBase2 function (storport.h)

## -description

The **StorPortGetDeviceBase2** function is like **[StorPortGetDeviceBase](nf-storport-storportgetdevicebase.md)**, but the *Flags* parameter allows for additional optional behavior. Rather than returning a mapped base address, a status is returned and the caller provides a pointer to store the mapping.

## -parameters

### -param HwDeviceExtension

Used to find port device extension.

### -param BusType

Specifies the type of bus, such as EISA, MCA, or ISA.

### -param SystemIoBusNumber

Specifies the IO bus for machines with multiple buses.

### -param Address

The base device address to be mapped.

### -param NumberOfBytes

The number of bytes for which *Address* is valid.

### -param InIoSpace

Indicates an IO address.

### -param Flags

Used to request different attributes when mapping *BaseAddress*. If *Flags* is zero, the mapping is non-cached read/write.

### -param BaseAddress

A pointer to store the base address mapping in.

## -returns

Returns a STOR_STATUS_xxx code.

| Return code | Description |
|--|--|
| STOR_STATUS_SUCCESS | The extended function was successfully returned. |
| STOR_STATUS_INVALID_PARAMETER | One of the *Flags* parameters is invalid. |
| STOR_STATUS_NOT_IMPLEMENTED | The specified extended function is not implemented. |

## -remarks

## -see-also

- **[StorPortGetDeviceBase](nf-storport-storportgetdevicebase.md)**
