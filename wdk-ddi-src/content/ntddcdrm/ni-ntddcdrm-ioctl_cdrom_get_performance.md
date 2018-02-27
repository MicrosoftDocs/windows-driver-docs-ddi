---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_PERFORMANCE
title: IOCTL_CDROM_GET_PERFORMANCE
author: windows-driver-content
description: Retrieves the supported speeds from the device. The IOCTL_CDROM_GET_PERFORMANCE I/O control request is a wrapper over the MMC command, GET PERFORMANCE.
old-location: storage\ioctl_cdrom_get_performance.htm
old-project: storage
ms.assetid: 3BA2D85A-052B-4851-B31C-072F2872F3FE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_CDROM_GET_PERFORMANCE, IOCTL_CDROM_GET_PERFORMANCE control code [Storage Devices], ntddcdrm/IOCTL_CDROM_GET_PERFORMANCE, storage.ioctl_cdrom_get_performance
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_GET_PERFORMANCE
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_PERFORMANCE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


Retrieves the supported speeds from the device. The <b>IOCTL_CDROM_GET_PERFORMANCE</b> 
   I/O control request   is a wrapper over the MMC command, GET PERFORMANCE.

To perform this operation, call the 
   <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function with   <b>IOCTL_CDROM_GET_PERFORMANCE</b> as the <i>dwIoControlCode</i> parameter.


## -ioctlparameters




### -input-buffer


<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> requests performance data.
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_write_speed_request.md">CDROM_WRITE_SPEED_REQUEST</a> requests write speed descriptor.


### -input-buffer-length

Length of a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>.


### -output-buffer

For request type CdromWriteSpeedRequest, this IOCTL returns the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a> structure followed by a number of CDROM_WRITE_SPEED_DESCRIPTOR descriptors.

For request type CdromPerformanceRequest, this  IOCTL returns the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a> structure followed by an optional descriptor. The descriptor following this header depends on the value in the <b>Except</b> field of the <b>CDROM_PERFORMANCE_HEADER</b> structure. If <b>Except</b> is false, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR is used; otherwise, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR is used.


### -output-buffer-length

Length of a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




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

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_write_speed_request.md">CDROM_WRITE_SPEED_REQUEST</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>



<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_PERFORMANCE control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

