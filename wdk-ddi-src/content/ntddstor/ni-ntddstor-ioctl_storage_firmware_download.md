---
UID: NI:ntddstor.IOCTL_STORAGE_FIRMWARE_DOWNLOAD
title: IOCTL_STORAGE_FIRMWARE_DOWNLOAD
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_FIRMWARE_DOWNLOAD to download a firmware image to a storage device, but does not activate it.
old-location: storage\ioctl_storage_firmware_download.htm
old-project: storage
ms.assetid: D5572EE3-C277-494C-B288-A6E8F8A26A3E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_STORAGE_FIRMWARE_DOWNLOAD, IOCTL_STORAGE_FIRMWARE_DOWNLOAD control code [Storage Devices], ntddstor/IOCTL_STORAGE_FIRMWARE_DOWNLOAD, storage.ioctl_storage_firmware_download
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_FIRMWARE_DOWNLOAD
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_FIRMWARE_DOWNLOAD IOCTL


## -description


A driver can use <b>IOCTL_STORAGE_FIRMWARE_DOWNLOAD</b> to download a firmware image to a storage device, but does not activate it. If the image to be downloaded is larger than the controller’s maximum data transfer size, this IOCTL will have to be called multiple times until the entire image is downloaded.


## -ioctlparameters




### -input-buffer

<b>
       Irp-&gt;AssociatedIrp.SystemBuffer</b> contains <a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_download.md">STORAGE_HW_FIRMWARE_DOWNLOAD</a> data that specifies information about the downloaded firmware to activate.


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_download.md">STORAGE_HW_FIRMWARE_DOWNLOAD</a>).


### -output-buffer

This IOCTL has no output structure.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_download.md">STORAGE_HW_FIRMWARE_DOWNLOAD</a>



<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_slot_info.md">STORAGE_HW_FIRMWARE_SLOT_INFO</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_firmware_activate.md">IOCTL_STORAGE_FIRMWARE_ACTIVATE</a>



<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_info_query.md">STORAGE_HW_FIRMWARE_INFO_QUERY</a>



<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_activate.md">STORAGE_HW_FIRMWARE_ACTIVATE</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_firmware_get_info.md">IOCTL_STORAGE_FIRMWARE_GET_INFO</a>



<a href="..\ntddstor\ns-ntddstor-_storage_hw_firmware_info.md">STORAGE_HW_FIRMWARE_INFO</a>



 

 


