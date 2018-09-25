---
UID: NE:sddef.SD_COMMAND_CLASS
title: SD_COMMAND_CLASS
author: windows-driver-content
description: The SD_COMMAND_CLASS enumeration lists the classes of Secure Digital (SD) card commands.
old-location: sd\sd_command_class.htm
tech.root: SD
ms.assetid: 2c82db4c-70b1-4601-a0b0-23b1f53e3503
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SD.sd_command_class, SDCC_APP_CMD, SDCC_STANDARD, SD_COMMAND_CLASS, SD_COMMAND_CLASS enumeration [Buses], sd-structs_ce4cd8ec-a512-422b-aed0-3052619f4f6a.xml, sddef/SDCC_APP_CMD, sddef/SDCC_STANDARD, sddef/SD_COMMAND_CLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sddef.h
api_name:
-	SD_COMMAND_CLASS
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




<a href="https://msdn.microsoft.com/7c49c394-d0b3-4594-a623-0a13825bdcec">SDCMD_DESCRIPTOR</a>
 

 

