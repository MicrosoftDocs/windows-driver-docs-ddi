---
UID: NI:ntdddisk.IOCTL_DISK_PERFORMANCE_OFF
title: IOCTL_DISK_PERFORMANCE_OFF (ntdddisk.h)
description: Disables the counters that were enabled by previous calls to IOCTL_DISK_PERFORMANCE. This request is available in Windows XP and later operating systems. Caller must be running at IRQL = PASSIVE_LEVEL.
old-location: storage\ioctl_disk_performance_off.htm
tech.root: storage
ms.assetid: 9a56ac86-2d39-4367-8e64-b6f6bc0da0ea
ms.date: 03/29/2018
keywords: ["IOCTL_DISK_PERFORMANCE_OFF IOCTL"]
ms.keywords: IOCTL_DISK_PERFORMANCE_OFF, IOCTL_DISK_PERFORMANCE_OFF control, IOCTL_DISK_PERFORMANCE_OFF control code [Storage Devices], k307_af1f6a33-e2e5-4ba0-96ad-f1d84c30ef76.xml, ntdddisk/IOCTL_DISK_PERFORMANCE_OFF, storage.ioctl_disk_performance_off
f1_keywords:
 - "ntdddisk/IOCTL_DISK_PERFORMANCE_OFF"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntdddisk.h
api_name:
- IOCTL_DISK_PERFORMANCE_OFF
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_PERFORMANCE_OFF IOCTL


## -description



Disables the counters that were enabled by previous calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_performance">IOCTL_DISK_PERFORMANCE</a>. This request is available in Windows XP and later operating systems. Caller must be running at IRQL = PASSIVE_LEVEL. 




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

The <b>Information</b> member is set to zero. The <b>Status</b> member is set to STATUS_SUCCESS if the operation was successful. Otherwise, the <b>Status</b> member is set to the appropriate error code. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_performance">IOCTL_DISK_PERFORMANCE</a>
 

 

