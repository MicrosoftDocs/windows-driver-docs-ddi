---
UID: NS:ntddcdrm._CDROM_PERFORMANCE_REQUEST
title: CDROM_PERFORMANCE_REQUEST (ntddcdrm.h)
description: The CDROM_PERFORMANCE_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request and describes the performance data requested.
old-location: storage\cdrom_performance_request.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["CDROM_PERFORMANCE_REQUEST structure"]
ms.keywords: "*PCDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST structure [Storage Devices], PCDROM_PERFORMANCE_REQUEST, PCDROM_PERFORMANCE_REQUEST structure pointer [Storage Devices], _CDROM_PERFORMANCE_REQUEST, ntddcdrm/CDROM_PERFORMANCE_REQUEST, ntddcdrm/PCDROM_PERFORMANCE_REQUEST, storage.cdrom_performance_request"
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: CDROM_PERFORMANCE_REQUEST, *PCDROM_PERFORMANCE_REQUEST
f1_keywords:
 - _CDROM_PERFORMANCE_REQUEST
 - ntddcdrm/_CDROM_PERFORMANCE_REQUEST
 - PCDROM_PERFORMANCE_REQUEST
 - ntddcdrm/PCDROM_PERFORMANCE_REQUEST
 - CDROM_PERFORMANCE_REQUEST
 - ntddcdrm/CDROM_PERFORMANCE_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - _CDROM_PERFORMANCE_REQUEST
 - PCDROM_PERFORMANCE_REQUEST
 - CDROM_PERFORMANCE_REQUEST
---

# CDROM_PERFORMANCE_REQUEST structure

## -description

The **CDROM_PERFORMANCE_REQUEST** structure is used as an input parameter to the [**IOCTL_CDROM_GET_PERFORMANCE**](ni-ntddcdrm-ioctl_cdrom_get_performance.md) I/O control request and describes the performance data requested.

## -struct-fields

### -field RequestType

The [**CDROM_PERFORMANCE_REQUEST_TYPE**](ne-ntddcdrm-_cdrom_performance_request_type.md) enumeration specifies the request type, **CdromPerformanceRequest**, or **CdromWriteSpeedRequest**.

### -field PerformanceType

The [**CDROM_PERFORMANCE_TYPE**](ne-ntddcdrm-_cdrom_performance_type.md) enumeration specifies the type of performance data.

### -field Exceptions

The [**CDROM_PERFORMANCE_EXCEPTION_TYPE**](ne-ntddcdrm-_cdrom_performance_exception_type.md)    enumeration specifies the type of exception.

### -field Tolerance

The [**CDROM_PERFORMANCE_TOLERANCE_TYPE**](ne-ntddcdrm-_cdrom_performance_tolerance_type.md) enumeration specifies the performance tolerance for the nominal performance and the time tolerance (seek delay) for the exception list.

### -field StaringLba

The starting logical block address field.

## -see-also

[**IOCTL_CDROM_GET_PERFORMANCE**](ni-ntddcdrm-ioctl_cdrom_get_performance.md)
