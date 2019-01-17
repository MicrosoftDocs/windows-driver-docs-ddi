---
UID: NS:1394._CONFIG_ROM
title: "_CONFIG_ROM"
description: The CONFIG_ROM structure is used to contain the first 24 bytes of an IEEE 1394 device's configuration ROM.
old-location: ieee\config_rom.htm
tech.root: IEEE
ms.assetid: 0ab96bc2-a89f-42cf-9ee2-020b47dff4cf
ms.date: 02/15/2018
ms.keywords: "*PCONFIG_ROM, 1394/CONFIG_ROM, 1394/PCONFIG_ROM, 1394stct_83c9e36a-b3d7-46cc-9dc6-1e40095d041b.xml, CONFIG_ROM, CONFIG_ROM structure [Buses], IEEE.config_rom, PCONFIG_ROM, PCONFIG_ROM structure pointer [Buses], _CONFIG_ROM"
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
api_name:
-	CONFIG_ROM
product:
- Windows
targetos: Windows
req.typenames: CONFIG_ROM, *PCONFIG_ROM
---

# _CONFIG_ROM structure


## -description


The CONFIG_ROM structure is used to contain the first 24 bytes of an IEEE 1394 device's configuration ROM.


## -struct-fields




### -field CR_Info

Specifies the first 4 bytes of the configuration ROM. 


### -field CR_Signiture

Specifies a signature that will be the same for all 1394 devices.


### -field CR_BusInfoBlockCaps

Specifies the bus capabilities of the device.


### -field CR_Node_UniqueID

Specifies the node's 64-bit vendor-assigned unique ID.


### -field CR_Root_Info

Specifies the first 4 bytes of the root directory information.


## -remarks



See the <a href="https://go.microsoft.com/fwlink/p/?linkid=8729">IEEE 1394 Trade Association specification</a> website for more details about the layout of the standard configuration ROM.



