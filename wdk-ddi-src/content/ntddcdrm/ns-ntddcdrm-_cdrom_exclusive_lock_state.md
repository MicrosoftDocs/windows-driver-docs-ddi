---
UID: NS:ntddcdrm._CDROM_EXCLUSIVE_LOCK_STATE
title: _CDROM_EXCLUSIVE_LOCK_STATE (ntddcdrm.h)
description: The CDROM_EXCLUSIVE_LOCK_STATE structure is used by the CD-ROM class driver to report the exclusive access state of a CD-ROM device.
old-location: storage\cdrom_exclusive_lock_state.htm
tech.root: storage
ms.assetid: ea5e60d9-d167-4ad9-bef4-2ebb6c63184d
ms.date: 03/29/2018
keywords: ["_CDROM_EXCLUSIVE_LOCK_STATE structure"]
ms.keywords: "*PCDROM_EXCLUSIVE_LOCK_STATE, CDROM_EXCLUSIVE_LOCK_STATE, CDROM_EXCLUSIVE_LOCK_STATE structure [Storage Devices], PCDROM_EXCLUSIVE_LOCK_STATE, PCDROM_EXCLUSIVE_LOCK_STATE structure pointer [Storage Devices], _CDROM_EXCLUSIVE_LOCK_STATE, ntddcdrm/CDROM_EXCLUSIVE_LOCK_STATE, ntddcdrm/PCDROM_EXCLUSIVE_LOCK_STATE, storage.cdrom_exclusive_lock_state, structs-CD-ROM_eeca8064-e141-4398-819e-451a80aca4c3.xml"
f1_keywords:
 - "ntddcdrm/CDROM_EXCLUSIVE_LOCK_STATE"
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
- CDROM_EXCLUSIVE_LOCK_STATE
product:
- Windows
targetos: Windows
req.typenames: CDROM_EXCLUSIVE_LOCK_STATE, *PCDROM_EXCLUSIVE_LOCK_STATE
---

# _CDROM_EXCLUSIVE_LOCK_STATE structure


## -description


The CDROM_EXCLUSIVE_LOCK_STATE structure is used by the CD-ROM class driver to report the exclusive access state of a CD-ROM device.


## -struct-fields




### -field LockState

A Boolean value that indicates whether the CD-ROM device is locked for exclusive access. If <b>TRUE</b>, the device is locked. If <b>FALSE</b>, the device is not locked.


### -field CallerName

A <b>NULL</b>-terminated string that identifies the application or system component that has a lock on the CD-ROM device. The length of the string must be less than or equal to CDROM_EXCLUSIVE_CALLER_LENGTH bytes, including the <b>NULL</b> character at the end of the string. The string must contain alphanumerics (A - Z, a - z, 0 - 9), spaces, periods, commas, colons (:), semi-colons (;), hyphens (-), and underscores (_).


## -remarks



The CD-ROM class driver reports the exclusive access state of a CD-ROM device in response to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_exclusive_access">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_exclusive_access">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>
 

 

