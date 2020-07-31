---
UID: NI:ntddstor.IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
title: IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES (ntddstor.h)
description: The IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request is sent to the storage class driver to determine available and used mapping resources on a storage device.
old-location: storage\ioctl_storage_get_lb_provisioning_map_resources.htm
tech.root: storage
ms.assetid: 117F6507-CA52-4EA7-9633-75ADB19F4DDA
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES IOCTL"]
ms.keywords: IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES, IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES control, IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES control code [Storage Devices], ntddstor/IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES, storage.ioctl_storage_get_lb_provisioning_map_resources
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES"
 - "IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- Ntddstor.h
api_name:
- IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES IOCTL


## -description


The <b>IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</b> request is sent to the storage class driver to determine available and used mapping resources on a storage device.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <i>Irp->AssociatedIrp.SystemBuffer</i> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_lb_provisioning_map_resources">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a> structure.


### -output-buffer-length

<i>Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(STORAGE_LB_PROVISIONING_MAP_RESOURCES).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.


## -remarks



If logical block provisioning is enabled on a LUN, resource mapping counts  may be reported from the storage device. Resource mapping information is obtained by using the <b>IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</b>  request. A storage monitoring application can use this IOCTL to query resource mapping conditions before a resource threshold or exhaustion event is logged.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_lb_provisioning_map_resources">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a>
 

 

