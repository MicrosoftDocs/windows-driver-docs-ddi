---
UID: NI:ntddstor.IOCTL_STORAGE_FIND_NEW_DEVICES
title: IOCTL_STORAGE_FIND_NEW_DEVICES (ntddstor.h)
description: Determines whether another device that the driver supports has been connected to the I/O bus, either since the system was booted or since the driver last processed this request.
old-location: storage\ioctl_storage_find_new_devices.htm
tech.root: storage
ms.assetid: 359169a3-602d-4910-badf-c777c1a804e7
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_FIND_NEW_DEVICES IOCTL"]
ms.keywords: IOCTL_STORAGE_FIND_NEW_DEVICES, IOCTL_STORAGE_FIND_NEW_DEVICES control, IOCTL_STORAGE_FIND_NEW_DEVICES control code [Storage Devices], k307_2bd9c727-e25a-4c21-9173-af7bc2c830c6.xml, ntddstor/IOCTL_STORAGE_FIND_NEW_DEVICES, storage.ioctl_storage_find_new_devices
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_FIND_NEW_DEVICES"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_FIND_NEW_DEVICES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_FIND_NEW_DEVICES IOCTL


## -description



Determines whether another device that the driver supports has been connected to the I/O bus, either since the system was booted or since the driver last processed this request. 

This IOCTL is obsolete in the Plug and Play environment. Plug and Play class drivers handle this request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinvalidatedevicerelations">IoInvalidateDeviceRelations</a> with the device relations type <b>BusRelations</b>. If a new device is found, the class driver's <i>AddDevice</i> routine will be called. 

Legacy class drivers can continue to handle this IOCTL without modifications. If a new device is found, the driver sets up any necessary system objects and resources to handle I/O requests for its new device. It also initializes the device on receipt of this request dynamically, that is, without requiring the machine to be rebooted. Such a driver is assumed to support devices connected on a dynamically configurable I/O bus.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field can be set to STATUS_SUCCESS or to any other value returned by a Plug and Play driver's <b>IoInvalidateDeviceRelations</b> call or a legacy driver's (re)initialization code.

