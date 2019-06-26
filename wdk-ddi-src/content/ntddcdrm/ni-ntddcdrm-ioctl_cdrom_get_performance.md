---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_PERFORMANCE
title: IOCTL_CDROM_GET_PERFORMANCE (ntddcdrm.h)
description: Retrieves the supported speeds from the device. The IOCTL_CDROM_GET_PERFORMANCE I/O control request is a wrapper over the MMC command, GET PERFORMANCE.
old-location: storage\ioctl_cdrom_get_performance.htm
tech.root: storage
ms.assetid: 3BA2D85A-052B-4851-B31C-072F2872F3FE
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_GET_PERFORMANCE, IOCTL_CDROM_GET_PERFORMANCE control, IOCTL_CDROM_GET_PERFORMANCE control code [Storage Devices], ntddcdrm/IOCTL_CDROM_GET_PERFORMANCE, storage.ioctl_cdrom_get_performance
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Winioctl.h
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
- ntddcdrm.h
api_name:
- IOCTL_CDROM_GET_PERFORMANCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_PERFORMANCE IOCTL


## -description


Retrieves the supported speeds from the device. The <b>IOCTL_CDROM_GET_PERFORMANCE</b> 
   I/O control request   is a wrapper over the MMC command, GET PERFORMANCE.

To perform this operation, call the 
   <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> 
   function with   <b>IOCTL_CDROM_GET_PERFORMANCE</b> as the <i>dwIoControlCode</i> parameter.


## -ioctlparameters




### -input-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a> requests performance data.
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_write_speed_request">CDROM_WRITE_SPEED_REQUEST</a> requests write speed descriptor.


### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a>.


### -output-buffer

For request type CdromWriteSpeedRequest, this IOCTL returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a> structure followed by a number of CDROM_WRITE_SPEED_DESCRIPTOR descriptors.

For request type CdromPerformanceRequest, this  IOCTL returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a> structure followed by an optional descriptor. The descriptor following this header depends on the value in the <b>Except</b> field of the <b>CDROM_PERFORMANCE_HEADER</b> structure. If <b>Except</b> is false, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR is used; otherwise, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR is used.


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. 

Because of  status code propagation from other APIs, the <b>Status</b> field can be set to (but is not limited to) the following:




#### -STATUS_BUFFER_TOO_SMALL

The output buffer length is smaller than required.


#### -STATUS_INFO_LENGTH_MISMATCH

The input buffer length is smaller than required.


#### -STATUS_INVALID_DEVICE_REQUEST

The device does not support this request.


#### -STATUS_INVALID_PARAMETER

The CDROM_PERFORMANCE_REQUEST header does not contain a valid combination of parameters specified by enumerations.


#### -STATUS_SUCCESS

The request completed successfully.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_header">CDROM_PERFORMANCE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_performance_request">CDROM_PERFORMANCE_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdrm/ns-ntddcdrm-_cdrom_write_speed_request">CDROM_WRITE_SPEED_REQUEST</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>
 

 

