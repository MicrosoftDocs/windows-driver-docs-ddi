---
UID: NI:ntddstor.IOCTL_STORAGE_FIRMWARE_GET_INFO
title: IOCTL_STORAGE_FIRMWARE_GET_INFO
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_FIRMWARE_GET_INFO to query a storage device for detailed firmware information.
old-location: storage\ioctl_storage_firmware_get_info.htm
old-project: storage
ms.assetid: AB5FA3A5-1187-4925-9EC0-62870851AED1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_STORAGE_FIRMWARE_GET_INFO, IOCTL_STORAGE_FIRMWARE_GET_INFO control code [Storage Devices], ntddstor/IOCTL_STORAGE_FIRMWARE_GET_INFO, storage.ioctl_storage_firmware_get_info
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
-	IOCTL_STORAGE_FIRMWARE_GET_INFO
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_FIRMWARE_GET_INFO IOCTL


## -description


A driver can use <b>IOCTL_STORAGE_FIRMWARE_GET_INFO</b> to query a storage device for detailed firmware information. A successful call will return information about firmware revisions, activity status, as well as read/write attributes for each slot. The amount of data returned will vary based on storage protocol.


## -ioctlparameters




### -input-buffer

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/dn931811">STORAGE_HW_FIRMWARE_INFO_QUERY</a>).

<b>
       Irp-&gt;AssociatedIrp.SystemBuffer</b> contains <a href="https://msdn.microsoft.com/library/windows/hardware/dn931811">STORAGE_HW_FIRMWARE_INFO_QUERY</a> data that specifies the target of the request. 

<b>
       Parameters.DeviceIoControl.OutputBufferLength</b> indicates the number of bytes that can be written to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. <b>OutputBufferLength</b> must be <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/dn931810">STORAGE_HW_FIRMWARE_INFO</a>) + <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/dn931812">STORAGE_HW_FIRMWARE_SLOT_INFO</a>) * (<b>STORAGE_HW_FIRMWARE_INFO.SlotCount</b> -1).


### -input-buffer-length

The length of .


### -output-buffer

The driver returns query data to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The output buffer should contain a <a href="https://msdn.microsoft.com/library/windows/hardware/dn931810">STORAGE_HW_FIRMWARE_INFO</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn931812">STORAGE_HW_FIRMWARE_SLOT_INFO</a> structure for each slot on the device.  


### -output-buffer-length

The length of .


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn932065">IOCTL_STORAGE_FIRMWARE_ACTIVATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn932066">IOCTL_STORAGE_FIRMWARE_DOWNLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931808">STORAGE_HW_FIRMWARE_ACTIVATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931809">STORAGE_HW_FIRMWARE_DOWNLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931810">STORAGE_HW_FIRMWARE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931811">STORAGE_HW_FIRMWARE_INFO_QUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn931812">STORAGE_HW_FIRMWARE_SLOT_INFO</a>
 

 

