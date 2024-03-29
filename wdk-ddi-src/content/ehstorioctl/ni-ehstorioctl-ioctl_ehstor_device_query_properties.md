---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
title: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES (ehstorioctl.h)
description: A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.
old-location: storage\ioctl_ehstor_device_query_properties.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES IOCTL"]
ms.keywords: IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES, IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES control, IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES, storage.ioctl_ehstor_device_query_properties
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
 - ehstorioctl/IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES
---

# IOCTL_EHSTOR_DEVICE_QUERY_PROPERTIES IOCTL


## -description

A silo driver sends this IOCTL to the storage device stack to query for storage device properties. The   Enhanced Storage Class Driver (EHSTOR) will handle the request and return the available properties.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The output buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure. <b>EHSTOR_DEVICE_PROPERTIES</b> is declared in <i>ehstorioctl.h</i> as the following.


```
typedef struct _EHSTOR_DEVICE_PROPERTIES
{
    ULONG  StructSize;
    ULONG  BytesPerSector;
} EHSTOR_DEVICE_PROPERTIES;
```


### -output-buffer-length

an  <b>EHSTOR_DEVICE_PROPERTIES</b>  structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

STATUS_SUCCESS is returned in the <b>Status</b> field if device properties are returned in the system buffer. Otherwise, another appropriate status code  is returned.

## -BytesPerSector

The size, in bytes, of a sector on the underlying storage device.

## -StructSize

The size of the structure. This is set to <b>sizeof</b>(EHSTOR_DEVICE_PROPERTIES).

## -remarks

Currently, bytes per sector is the only property available in <b>EHSTOR_DEVICE_PROPERTIES</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ehstorioctl/ns-ehstorioctl-tagact_authz_state">SILO_DRIVER_CAPABILITES</a>
