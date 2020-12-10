---
UID: NS:ntddcdrm._CDROM_PERFORMANCE_HEADER
title: _CDROM_PERFORMANCE_HEADER (ntddcdrm.h)
description: The CDROM_PERFORMANCE_HEADER structure is used by the IOCTL_CDROM_GET_PERFORMANCE IOCTL to return data. When the request type is CdromPerformanceRequest, the IOCTL returns this header followed by optional descriptors.
old-location: storage\cdrom_performance_header.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CDROM_PERFORMANCE_HEADER structure"]
ms.keywords: "*PCDROM_PERFORMANCE_HEADER, CDROM_PERFORMANCE_HEADER, CDROM_PERFORMANCE_HEADER structure [Storage Devices], PCDROM_PERFORMANCE_HEADER, PCDROM_PERFORMANCE_HEADER structure pointer [Storage Devices], _CDROM_PERFORMANCE_HEADER, ntddcdrm/CDROM_PERFORMANCE_HEADER, ntddcdrm/PCDROM_PERFORMANCE_HEADER, storage.cdrom_performance_header"
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
req.typenames: CDROM_PERFORMANCE_HEADER, *PCDROM_PERFORMANCE_HEADER
f1_keywords:
 - _CDROM_PERFORMANCE_HEADER
 - ntddcdrm/_CDROM_PERFORMANCE_HEADER
 - PCDROM_PERFORMANCE_HEADER
 - ntddcdrm/PCDROM_PERFORMANCE_HEADER
 - CDROM_PERFORMANCE_HEADER
 - ntddcdrm/CDROM_PERFORMANCE_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - CDROM_PERFORMANCE_HEADER
---

# _CDROM_PERFORMANCE_HEADER structure


## -description

The CDROM_PERFORMANCE_HEADER structure is used by the  <a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>  IOCTL to  return data.  When the request type is  CdromPerformanceRequest, the IOCTL returns this header followed by optional descriptors.

## -struct-fields

### -field DataLength

The size of the available data (not just the size of returned data). The size does  not include this <b>Datalength</b> field.

### -field Except

The format of the descriptors that follow the header depend on the value in this field. If false (0), the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_nominal_performance_descriptor">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a> follows the <b>CDROM_PERFORMANCE_HEADER</b> in the returned data. If true (1),  the <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exception_performance_descriptor">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a> follows the <b>CDROM_PERFORMANCE_HEADER</b> in the returned data.

### -field Write

Indicates whether the result data is for read or write performance.  If false (0), it indicates that the result data is for read performance. If true (1), it indicates that the result data is for write performance.

### -field Reserved1

Reserved.

### -field Reserved2

Reserved.

### -field Data

Contains a list of the following records, depending upon the type of request: <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_nominal_performance_descriptor">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a>,   
    <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exception_performance_descriptor">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a>,   
    <a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_write_speed_descriptor">CDROM_WRITE_SPEED_DESCRIPTOR</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_exception_performance_descriptor">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_nominal_performance_descriptor">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_write_speed_descriptor">CDROM_WRITE_SPEED_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>
