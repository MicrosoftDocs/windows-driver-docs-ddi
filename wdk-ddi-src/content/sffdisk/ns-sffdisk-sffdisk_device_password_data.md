---
UID: NS:sffdisk._SFFDISK_DEVICE_PASSWORD_DATA
tech.root: sd
title: SFFDISK_DEVICE_PASSWORD_DATA
ms.date: 10/06/2022
targetos: Windows
description: Learn more about the SFFDISK_DEVICE_PASSWORD_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: sffdisk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: SFFDISK_DEVICE_PASSWORD_DATA, *PSFFDISK_DEVICE_PASSWORD_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sffdisk.h
api_name:
 - _SFFDISK_DEVICE_PASSWORD_DATA
 - PSFFDISK_DEVICE_PASSWORD_DATA
 - SFFDISK_DEVICE_PASSWORD_DATA
f1_keywords:
 - _SFFDISK_DEVICE_PASSWORD_DATA
 - sffdisk/_SFFDISK_DEVICE_PASSWORD_DATA
 - PSFFDISK_DEVICE_PASSWORD_DATA
 - sffdisk/PSFFDISK_DEVICE_PASSWORD_DATA
 - SFFDISK_DEVICE_PASSWORD_DATA
 - sffdisk/SFFDISK_DEVICE_PASSWORD_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _SFFDISK_DEVICE_PASSWORD_DATA
---

## -description

The SFFDISK\_DEVICE\_PASSWORD\_DATA structure is used in conjunction with an [**IOCTL\_SFFDISK\_DEVICE\_PASSWORD**](ni-sffdisk-ioctl_sffdisk_device_password.md) to change the password on a Secure Digital (SD) card.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Reserved

Reserved.

### -field Command

Contains a structure of type [**SFFDISK\_DPCMD**](ne-sffdisk-sffdisk_dpcmd.md) that defines the type of operation.

### -field Information

On output, this member contains the return value for the operation.

### -field PasswordLength

The length, in bytes, of the current password.

### -field NewPasswordLength

The length, in bytes, of the new password.

### -field Data[0]

Buffer that the caller uses to pass in both the old and the new password. The current (old) password is at the beginning of the buffer and is immediately followed by the new password.

## -see-also

[**IOCTL\_SFFDISK\_DEVICE\_PASSWORD**](ni-sffdisk-ioctl_sffdisk_device_password.md)
