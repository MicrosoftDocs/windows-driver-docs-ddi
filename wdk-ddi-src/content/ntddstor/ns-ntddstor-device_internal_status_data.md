---
UID: NS:ntddstor._DEVICE_INTERNAL_STATUS_DATA
title: DEVICE_INTERNAL_STATUS_DATA
author: windows-driver-content
description: 
tech.root: storage
ms.assetid: 910ff4a4-e0e3-4402-8231-c3d62afe2ea4
ms.author: windowsdriverdev
ms.date: 11/30/2019
ms.topic: struct
f1_keywords:
 - "ntddstor/DEVICE_INTERNAL_STATUS_DATA"
 - "DEVICE_INTERNAL_STATUS_DATA"
ms.keywords: DEVICE_INTERNAL_STATUS_DATA, DEVICE_INTERNAL_STATUS_DATA, *PDEVICE_INTERNAL_STATUS_DATA, 
req.header: ntddstor.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DEVICE_INTERNAL_STATUS_DATA, *PDEVICE_INTERNAL_STATUS_DATA
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddstor.h
api_name: 
 - DEVICE_INTERNAL_STATUS_DATA
product: 
 - Windows
targetos: Windows
---

# DEVICE_INTERNAL_STATUS_DATA structure

## -description

A device returns its internal error history data in a DEVICE_INTERNAL_STATUS_DATA structure during an [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md) request.

## -struct-fields

### -field Version

Version of this structure. Set to **sizeof**(DEVICE_INTERNAL_STATUS_DATA).

### -field Size

Total size in bytes of this structure. Set to **sizeof**(DEVICE_INTERNAL_STATUS_DATA) plus the device's internal data size specified by **StatusDataLength**.

### -field T10VendorId

The Vendor ID defined by T10 industry association.

### -field DataSet1Length

Specifies the data length for data set 1.

### -field DataSet2Length

Specifies the data length for data set 2.

### -field DataSet3Length

Specifies the data length for data set 3.

### -field DataSet4Length

Specifies the data length for data set 4.

### -field StatusDataVersion

Specifies the data version.

### -field Reserved

Reserved; do not use.

### -field ReasonIdentifier

Specifies the device internal status when the status data is generated.

### -field StatusDataLength

Size, in bytes, of the entire buffer that *StatusData* points to.

### -field StatusData

Pointer to the status data header, which is always 512 bytes in size. The actual data follows the status data header.

## -remarks

DEVICE_INTERNAL_STATUS_DATA is the output buffer for [IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md). The device will return its error history data in this structure.

See the SCSI specification for more information.

## -see-also

[IOCTL_STORAGE_GET_DEVICE_INTERNAL_LOG](ni-ntddstor-ioctl_storage_get_device_internal_log.md)
