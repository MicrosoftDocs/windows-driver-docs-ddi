---
UID: NS:ntddpar._PAR_DEVICE_ID_SIZE_INFORMATION
title: _PAR_DEVICE_ID_SIZE_INFORMATION (ntddpar.h)
description: The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a NULL terminator.
old-location: parports\par_device_id_size_information.htm
tech.root: parports
ms.assetid: b48624cd-e8fb-4152-8e34-9cb1e542f62b
ms.date: 02/15/2018
keywords: ["PAR_DEVICE_ID_SIZE_INFORMATION structure"]
ms.keywords: "*PPAR_DEVICE_ID_SIZE_INFORMATION, PAR_DEVICE_ID_SIZE_INFORMATION, PAR_DEVICE_ID_SIZE_INFORMATION structure [Parallel Ports], PPAR_DEVICE_ID_SIZE_INFORMATION, PPAR_DEVICE_ID_SIZE_INFORMATION structure pointer [Parallel Ports], _PAR_DEVICE_ID_SIZE_INFORMATION, cisspd_388a088d-9dd7-4a6c-99ad-b1e725d91f72.xml, ntddpar/PAR_DEVICE_ID_SIZE_INFORMATION, ntddpar/PPAR_DEVICE_ID_SIZE_INFORMATION, parports.par_device_id_size_information"
f1_keywords:
 - "ntddpar/PAR_DEVICE_ID_SIZE_INFORMATION"
 - "PAR_DEVICE_ID_SIZE_INFORMATION"
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddpar.h
api_name:
- PAR_DEVICE_ID_SIZE_INFORMATION
targetos: Windows
req.typenames: PAR_DEVICE_ID_SIZE_INFORMATION, *PPAR_DEVICE_ID_SIZE_INFORMATION
---

# _PAR_DEVICE_ID_SIZE_INFORMATION structure


## -description


The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a <b>NULL</b> terminator.


## -syntax


```cpp
typedef struct _PAR_DEVICE_ID_SIZE_INFORMATION {
  ULONG DeviceIdSize;
} PAR_DEVICE_ID_SIZE_INFORMATION, *PPAR_DEVICE_ID_SIZE_INFORMATION;
```


## -struct-fields




### -field DeviceIdSize

Specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a <b>NULL</b> terminator.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id_size.md">IOCTL_PAR_QUERY_DEVICE_ID_SIZE</a>



 

 


