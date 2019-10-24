---
UID: NE:sddef.__unnamed_enum_0
title: SD_COMMAND_CLASS (sddef.h)
description: The SD_COMMAND_CLASS enumeration lists the classes of Secure Digital (SD) card commands.
old-location: sd\sd_command_class.htm
tech.root: SD
ms.assetid: 2c82db4c-70b1-4601-a0b0-23b1f53e3503
ms.date: 02/15/2018
ms.keywords: SD.sd_command_class, SDCC_APP_CMD, SDCC_STANDARD, SD_COMMAND_CLASS, SD_COMMAND_CLASS enumeration [Buses], sd-structs_ce4cd8ec-a512-422b-aed0-3052619f4f6a.xml, sddef/SDCC_APP_CMD, sddef/SDCC_STANDARD, sddef/SD_COMMAND_CLASS
ms.topic: enum
f1_keywords:
 - "sddef/SD_COMMAND_CLASS"
req.header: sddef.h
req.include-header: Sddef.h
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
- sddef.h
api_name:
- SD_COMMAND_CLASS
product:
- Windows
targetos: Windows
req.typenames: SD_COMMAND_CLASS
---

# SD_COMMAND_CLASS enumeration


## -description


The SD_COMMAND_CLASS enumeration lists the classes of Secure Digital (SD) card commands.


## -enum-fields




### -field SDCC_STANDARD

Indicates an SD card command from the standard command set. This command set includes command codes 0 to 63.


### -field SDCC_APP_CMD

Indicates an SD command from the application command set. This command set includes command codes 0 to 63, preceded by the application command escape code 55.

SD card drivers should not issue CMD55 (APP_CMD) commands through the SD bus interface. The bus driver will automatically issue the CMD55 command on behalf of the SD card driver when the command class is SDCC_APP_CMD.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sddef/ns-sddef-_sdcmd_descriptor">SDCMD_DESCRIPTOR</a>
 

 

