---
UID: NE:sffdisk.SFFDISK_DCMD
title: SFFDISK_DCMD (sffdisk.h)
description: The SFFDISK_DCMD enumeration identifies the type of Secure Digital (SD) card operation.
old-location: sd\sffdisk_dcmd.htm
tech.root: SD
ms.date: 02/15/2018
keywords: ["SFFDISK_DCMD enumeration"]
ms.keywords: SD.sffdisk_dcmd, SFFDISK_DCMD, SFFDISK_DCMD enumeration [Buses], SFFDISK_DC_DEVICE_COMMAND, SFFDISK_DC_GET_VERSION, SFFDISK_DC_LOCK_CHANNEL, SFFDISK_DC_UNLOCK_CHANNEL, sd-structs_440acb4f-89ba-4ea0-9f8b-c7fd241dfe85.xml, sffdisk/SFFDISK_DCMD, sffdisk/SFFDISK_DC_DEVICE_COMMAND, sffdisk/SFFDISK_DC_GET_VERSION, sffdisk/SFFDISK_DC_LOCK_CHANNEL, sffdisk/SFFDISK_DC_UNLOCK_CHANNEL
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
targetos: Windows
req.typenames: SFFDISK_DCMD
f1_keywords:
 - SFFDISK_DCMD
 - sffdisk/SFFDISK_DCMD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sffdisk.h
api_name:
 - SFFDISK_DCMD
---

# SFFDISK_DCMD enumeration


## -description

The SFFDISK_DCMD enumeration identifies the type of Secure Digital (SD) card operation.

## -enum-fields

### -field SFFDISK_DC_GET_VERSION

The operations retrieves the version of the card.

### -field SFFDISK_DC_LOCK_CHANNEL

The operation locks the interface channel.

### -field SFFDISK_DC_UNLOCK_CHANNEL

The operation unlocks the interface channel.

### -field SFFDISK_DC_DEVICE_COMMAND

The operation executes a device command.

## -remarks

Applications that submit IOCTL_SFFDISK_DEVICE_COMMAND requests to the SD stack use this enumeration to specify the type of operation. The application must assign one of the values of this enumeration to the <b>Command</b> member of the <a href="/previous-versions/windows/hardware/drivers/ff538133(v=vs.85)">SFFDISK_DEVICE_COMMAND_DATA</a> structure.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff538133(v=vs.85)">SFFDISK_DEVICE_COMMAND_DATA</a>

