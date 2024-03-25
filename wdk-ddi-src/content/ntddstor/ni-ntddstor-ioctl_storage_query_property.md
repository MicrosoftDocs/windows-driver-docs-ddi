---
UID: NI:ntddstor.IOCTL_STORAGE_QUERY_PROPERTY
title: IOCTL_STORAGE_QUERY_PROPERTY (ntddstor.h)
description: A driver can use IOCTL_STORAGE_QUERY_PROPERTY to return properties of a storage device or adapter.
old-location: storage\ioctl_storage_query_property.htm
tech.root: storage
ms.date: 12/09/2021
keywords: ["IOCTL_STORAGE_QUERY_PROPERTY IOCTL"]
ms.keywords: IOCTL_STORAGE_QUERY_PROPERTY, IOCTL_STORAGE_QUERY_PROPERTY control, IOCTL_STORAGE_QUERY_PROPERTY control code [Storage Devices], k307_1ee2fd05-4e88-47ef-8ed5-0553bcccc0d7.xml, ntddstor/IOCTL_STORAGE_QUERY_PROPERTY, storage.ioctl_storage_query_property
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.typenames: 
f1_keywords:
 - IOCTL_STORAGE_QUERY_PROPERTY
 - ntddstor/IOCTL_STORAGE_QUERY_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddstor.h
api_name:
 - IOCTL_STORAGE_QUERY_PROPERTY
---

# IOCTL_STORAGE_QUERY_PROPERTY IOCTL

## -description

A driver can use **IOCTL_STORAGE_QUERY_PROPERTY** to return properties of a storage device or adapter. The request indicates the kind of information to retrieve, such as inquiry data for a device or capabilities and limitations of an adapter. **IOCTL_STORAGE_QUERY_PROPERTY** can also be used to determine whether the port driver supports a particular property or which fields in the property descriptor can be modified with a subsequent change-property request.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= **sizeof**([**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)).

**Irp->AssociatedIrp.SystemBuffer** contains [**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md) data that specifies whether to query the device or the adapter, the type of query to perform, and any additional parameters required for the query, such as the page code for a particular SCSI mode sense page. Device properties must be retrieved only from a device; attempting to retrieve device properties from an adapter will cause an error.

**Parameters.DeviceIoControl.OutputBufferLength** indicates the number of bytes that can be written to **Irp->AssociatedIrp.SystemBuffer**. **OutputBufferLength** can be zero to determine whether a property exists without retrieving its data.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the parameter buffer at **Irp->AssociatedIrp.SystemBuffer**, which must be >= **sizeof**([**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)).

### -output-buffer

The driver returns query data to the buffer at **Irp->AssociatedIrp.SystemBuffer**. Varying amounts of bus-specific data can be appended to the structure.

### -output-buffer-length

Cast the structure returned to a [**STORAGE_DESCRIPTOR_HEADER**](ns-ntddstor-_storage_descriptor_header.md) and check its **Size** member to determine the number of bytes the structure actually requires.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The **Information** field is set to the number of bytes returned. The **Status** field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED.

## -see-also

[**STORAGE_DESCRIPTOR_HEADER**](ns-ntddstor-_storage_descriptor_header.md)

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)

[**STORAGE_RPMB_DATA_FRAME**](ns-ntddstor-storage_rpmb_data_frame.md)
