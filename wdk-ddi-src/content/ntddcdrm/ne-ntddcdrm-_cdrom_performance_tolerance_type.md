---
UID: NE:ntddcdrm._CDROM_PERFORMANCE_TOLERANCE_TYPE
title: _CDROM_PERFORMANCE_TOLERANCE_TYPE (ntddcdrm.h)
description: The CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration defines the allowable tolerances for performance data. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location: storage\cdrom_performance_tolerance_type.htm
tech.root: storage
ms.assetid: 2369582F-D042-474D-9191-F9E7BDD3725E
ms.date: 03/29/2018
keywords: ["CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration"]
ms.keywords: "*PCDROM_PERFORMANCE_TOLERANCE_TYPE, CDROM_PERFORMANCE_TOLERANCE_TYPE, CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration [Storage Devices], Cdrom10Nominal20Exceptions, PCDROM_PERFORMANCE_TOLERANCE_TYPE, PCDROM_PERFORMANCE_TOLERANCE_TYPE enumeration pointer [Storage Devices], _CDROM_PERFORMANCE_TOLERANCE_TYPE, ntddcdrm/ Cdrom10Nominal20Exceptions, ntddcdrm/CDROM_PERFORMANCE_TOLERANCE_TYPE, ntddcdrm/PCDROM_PERFORMANCE_TOLERANCE_TYPE, storage.cdrom_performance_tolerance_type"
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
req.typenames: CDROM_PERFORMANCE_TOLERANCE_TYPE, *PCDROM_PERFORMANCE_TOLERANCE_TYPE
f1_keywords:
 - _CDROM_PERFORMANCE_TOLERANCE_TYPE
 - ntddcdrm/_CDROM_PERFORMANCE_TOLERANCE_TYPE
 - PCDROM_PERFORMANCE_TOLERANCE_TYPE
 - ntddcdrm/PCDROM_PERFORMANCE_TOLERANCE_TYPE
 - CDROM_PERFORMANCE_TOLERANCE_TYPE
 - ntddcdrm/CDROM_PERFORMANCE_TOLERANCE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdrm.h
api_name:
 - CDROM_PERFORMANCE_TOLERANCE_TYPE
---

# _CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration


## -description

The <b>CDROM_PERFORMANCE_TOLERANCE_TYPE</b> enumeration defines the allowable tolerances for performance data. It is a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request.

## -enum-fields

### -field Cdrom10Nominal20Exceptions

Specifies that the descriptors returned have a 10% performance tolerance for the nominal performance and a 20% time tolerance for the exception list.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_get_performance">IOCTL_CDROM_GET_PERFORMANCE</a>

