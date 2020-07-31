---
UID: NE:sffdisk.__unnamed_enum_1
title: SFFDISK_DPCMD (sffdisk.h)
description: The SFFDISK_DPCMD enumeration lists the operations performed by an IOCTL_SFFDISK_DEVICE_PASSWORD request.
old-location: sd\sffdisk_dpcmd.htm
tech.root: SD
ms.assetid: 55a034e7-68fa-4f4a-b7c6-da215405375a
ms.date: 02/15/2018
keywords: ["SFFDISK_DPCMD enumeration"]
ms.keywords: SD.sffdisk_dpcmd, SFFDISK_DPCMD, SFFDISK_DPCMD enumeration [Buses], SFFDISK_DP_IS_SUPPORTED, SFFDISK_DP_LOCK_DEVICE, SFFDISK_DP_RESET_DEVICE_ALL_DATA, SFFDISK_DP_SET_PASSWORD, SFFDISK_DP_UNLOCK_DEVICE, sd-structs_794e7b1e-49e0-4385-ab34-235f00e1a7b2.xml, sffdisk/SFFDISK_DPCMD, sffdisk/SFFDISK_DP_IS_SUPPORTED, sffdisk/SFFDISK_DP_LOCK_DEVICE, sffdisk/SFFDISK_DP_RESET_DEVICE_ALL_DATA, sffdisk/SFFDISK_DP_SET_PASSWORD, sffdisk/SFFDISK_DP_UNLOCK_DEVICE
f1_keywords:
 - "sffdisk/SFFDISK_DPCMD"
 - "SFFDISK_DPCMD"
req.header: sffdisk.h
req.include-header: Sffdisk.h
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
- sffdisk.h
api_name:
- SFFDISK_DPCMD
targetos: Windows
req.typenames: SFFDISK_DPCMD
---

# SFFDISK_DPCMD enumeration


## -description


The SFFDISK_DPCMD enumeration lists the operations performed by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sffdisk/ni-sffdisk-ioctl_sffdisk_device_password">IOCTL_SFFDISK_DEVICE_PASSWORD</a> request.


## -enum-fields




### -field SFFDISK_DP_IS_SUPPORTED

The operation requests verification from the card that it supports command class 7.


### -field SFFDISK_DP_SET_PASSWORD

The operation sets the password.


### -field SFFDISK_DP_LOCK_DEVICE

The operation locks the device.


### -field SFFDISK_DP_UNLOCK_DEVICE

The operation unlocks the device.


### -field SFFDISK_DP_RESET_DEVICE_ALL_DATA

The operation resets the device.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff538136(v=vs.85)">SFFDISK_DEVICE_PASSWORD_DATA</a>
 

 

