---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_CONFIGURATION
title: IOCTL_CDROM_GET_CONFIGURATION (ntddcdrm.h)
description: Requests feature and profile information from a CD-ROM device.
old-location: storage\ioctl_cdrom_get_configuration.htm
tech.root: storage
ms.assetid: 2eb4b5c3-db06-4d21-8937-847734d7ac2f
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_GET_CONFIGURATION, IOCTL_CDROM_GET_CONFIGURATION control, IOCTL_CDROM_GET_CONFIGURATION control code [Storage Devices], k307_355fe40f-4056-4bd7-8e79-8824c38589f6.xml, ntddcdrm/IOCTL_CDROM_GET_CONFIGURATION, storage.ioctl_cdrom_get_configuration
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_GET_CONFIGURATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdrm.h
api_name:
- IOCTL_CDROM_GET_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_CONFIGURATION IOCTL


## -description



Requests feature and profile information from a CD-ROM device. 

Multimedia devices have different characteristics depending on the type of media that is in the device. To provide drivers with a means of querying multimedia devices about these varying characteristics, the <i>SCSI Multimedia - 3</i> (<i>MMC-3</i>) specification defines a command called "GET CONFIGURATION." This command permits drivers to query a device for both permanent information about the device and information that varies whenever the media changes. In Microsoft Windows 2000 and later operating systems, drivers can send this query to a device using the IOCTL_CDROM_GET_CONFIGURATION request. 

The IOCTL_CDROM_GET_CONFIGURATION request returns a list of descriptors that describe the capabilities of the device for the current medium. These descriptors are divided into two groups called "feature descriptors" and "profile list descriptors." A feature specifies the capabilities of a device and its associated medium. A profile is a collection of features. If the device supports a profile, it supports all the features in the profile. 

See the <i>MMC-3</i> specification for further discussion concerning features and profiles.




## -ioctlparameters




### -input-buffer

Input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the IO_STACK_LOCATION structure indicates the size, in bytes, of the input buffer, which must be = <b>sizeof</b>(GET_CONFIGURATION_IOCTL_INPUT).


### -output-buffer

The driver returns the feature and profile data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>. The data begins with a header of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_get_configuration_header">GET_CONFIGURATION_HEADER</a>. Feature data is reported in the space immediately following this header. Its size and formatting depend on which features are reported. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be >= <b>sizeof</b>(GET_CONFIGURATION_HEADER).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes that are returned. The <b>Status</b> field is set to STATUS_SUCCESS if the request succeeds. If the <b>Parameters.DeviceIoControl.InputBufferLength</b> does not have the correct value, the request fails with a STATUS_INFO_LENGTH_MISMATCH error. If <b>Parameters.DeviceIoControl.OutputBufferLength</b> is not large enough, the request fails with a STATUS_BUFFER_TOO_SMALL error. If the value for the output buffer is too large, the request fails a STATUS_INVALID_BUFFER_SIZE message. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_get_configuration_header">GET_CONFIGURATION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddmmc/ns-ntddmmc-_get_configuration_ioctl_input">GET_CONFIGURATION_IOCTL_INPUT</a>
 

 

