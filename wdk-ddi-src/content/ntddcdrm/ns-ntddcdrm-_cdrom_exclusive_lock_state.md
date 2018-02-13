---
UID: NS:ntddcdrm._CDROM_EXCLUSIVE_LOCK_STATE
title: "_CDROM_EXCLUSIVE_LOCK_STATE"
author: windows-driver-content
description: The CDROM_EXCLUSIVE_LOCK_STATE structure is used by the CD-ROM class driver to report the exclusive access state of a CD-ROM device.
old-location: storage\cdrom_exclusive_lock_state.htm
old-project: storage
ms.assetid: ea5e60d9-d167-4ad9-bef4-2ebb6c63184d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-CD-ROM_eeca8064-e141-4398-819e-451a80aca4c3.xml, storage.cdrom_exclusive_lock_state, CDROM_EXCLUSIVE_LOCK_STATE structure [Storage Devices], ntddcdrm/PCDROM_EXCLUSIVE_LOCK_STATE, CDROM_EXCLUSIVE_LOCK_STATE, PCDROM_EXCLUSIVE_LOCK_STATE, _CDROM_EXCLUSIVE_LOCK_STATE, ntddcdrm/CDROM_EXCLUSIVE_LOCK_STATE, *PCDROM_EXCLUSIVE_LOCK_STATE, PCDROM_EXCLUSIVE_LOCK_STATE structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	CDROM_EXCLUSIVE_LOCK_STATE
product: Windows
targetos: Windows
req.typenames: CDROM_EXCLUSIVE_LOCK_STATE, *PCDROM_EXCLUSIVE_LOCK_STATE
---

# _CDROM_EXCLUSIVE_LOCK_STATE structure


## -description


The CDROM_EXCLUSIVE_LOCK_STATE structure is used by the CD-ROM class driver to report the exclusive access state of a CD-ROM device.


## -syntax


````
typedef struct _CDROM_EXCLUSIVE_LOCK_STATE {
  BOOLEAN LockState;
  UCHAR   CallerName[CDROM_EXCLUSIVE_CALLER_LENGTH];
} CDROM_EXCLUSIVE_LOCK_STATE, *PCDROM_EXCLUSIVE_LOCK_STATE;
````


## -struct-fields




### -field LockState

A Boolean value that indicates whether the CD-ROM device is locked for exclusive access. If <b>TRUE</b>, the device is locked. If <b>FALSE</b>, the device is not locked.


### -field CallerName

A <b>NULL</b>-terminated string that identifies the application or system component that has a lock on the CD-ROM device. The length of the string must be less than or equal to CDROM_EXCLUSIVE_CALLER_LENGTH bytes, including the <b>NULL</b> character at the end of the string. The string must contain alphanumerics (A - Z, a - z, 0 - 9), spaces, periods, commas, colons (:), semi-colons (;), hyphens (-), and underscores (_).


## -remarks



The CD-ROM class driver reports the exclusive access state of a CD-ROM device in response to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a> request.




## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_exclusive_access.md">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_EXCLUSIVE_LOCK_STATE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

