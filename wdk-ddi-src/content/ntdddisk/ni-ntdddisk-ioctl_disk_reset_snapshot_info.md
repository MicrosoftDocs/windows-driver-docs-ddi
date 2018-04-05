---
UID: NI:ntdddisk.IOCTL_DISK_RESET_SNAPSHOT_INFO
title: IOCTL_DISK_RESET_SNAPSHOT_INFO
author: windows-driver-content
description: Clears all volume shadow copy service (VSS) hardware-based snapshot information from the disk.
old-location: storage\ioctl_disk_reset_snapshot_info.htm
old-project: storage
ms.assetid: b22b00de-4711-4896-a21c-33fbc7b1d64e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_RESET_SNAPSHOT_INFO, IOCTL_DISK_RESET_SNAPSHOT_INFO control code [Storage Devices], k307_3c2ed554-3774-467f-80a0-5017439a0aad.xml, ntdddisk/IOCTL_DISK_RESET_SNAPSHOT_INFO, storage.ioctl_disk_reset_snapshot_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntdddisk.h
api_name:
-	IOCTL_DISK_RESET_SNAPSHOT_INFO
product:
- Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_RESET_SNAPSHOT_INFO IOCTL


## -description



Clears all volume shadow copy service (VSS) hardware-based snapshot information from the disk. A snapshot is also known as a shadow copy. This request is available in Windows Vista and later versions of the Windows operating systems. The caller must be running at IRQL = PASSIVE_LEVEL.




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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> member is set to zero. The <b>Status</b> member is set to STATUS_SUCCESS if the operation was successful. Otherwise, the <b>Status</b> member is set to the appropriate error code. 


## -remarks



This I/O control code can be issued from either a kernel-mode driver or a user-mode application. When this I/O control code is issued from a kernel-mode driver, the caller provides an I/O Request Packet (IRP) that contains an IO_STATUS_BLOCK data structure. This data structure is used to return error information to the caller. When this I/O control code is issued from a user-mode application with the <b>DeviceIocontrol</b> routine, the caller can obtain error information by calling the <b>GetLastError</b> routine.

The disk whose handle is used when this IOCTL is issued might be in the offline state when the IOCTL is issued. If the disk is put in the offline state by using the disk manager Microsoft Management Console (MMC) snap-in, the disk will have its read-only attribute set, which will cause this IOCTL to fail. However, if the disk partition utility (Diskpart.exe) is used to put the disk in the offline state, the read-only attribute for the disk is not set. For this reason, it is best to use the disk partition utility to put a disk in the offline state.

<div class="alert"><b>Note</b>  A side effect of using this IOCTL is that Disk Management tools may report an additional partition of the type "UNKNOWN" on GPT disks. This 256 kilobyte partition is created by the IOCTL operation and is a snapshot partition used in the restore process. This partition is expected and can be ignored by system administrators.

</div>
<div> </div>


