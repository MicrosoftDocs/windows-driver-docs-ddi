---
UID: NS:1394._IRB_REQ_GET_CONFIG_ROM
title: _IRB_REQ_GET_CONFIG_ROM (1394.h)
description: This structure contains the fields necessary for the bus driver to carry out a GetConfigRom request.
old-location: ieee\irb_req_get_config_rom.htm
tech.root: IEEE
ms.assetid: 9C4EC9CA-3B7F-4611-BB96-A86C0FEDDF25
ms.date: 02/15/2018
keywords: ["IRB_REQ_GET_CONFIG_ROM structure"]
ms.keywords: 1394/IRB_REQ_GET_CONFIG_ROM, IEEE.irb_req_get_config_rom, IRB_REQ_GET_CONFIG_ROM, IRB_REQ_GET_CONFIG_ROM structure [Buses], _IRB_REQ_GET_CONFIG_ROM
f1_keywords:
 - "1394/IRB_REQ_GET_CONFIG_ROM"
 - "IRB_REQ_GET_CONFIG_ROM"
req.header: 1394.h
req.include-header: 
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
- 1394.h
api_name:
- IRB_REQ_GET_CONFIG_ROM
targetos: Windows
req.typenames: IRB_REQ_GET_CONFIG_ROM
---

# _IRB_REQ_GET_CONFIG_ROM structure


## -description


This structure contains the fields necessary for the bus driver to carry out a GetConfigRom request.


## -struct-fields




### -field GenerationCount

Receives the generation of the bus for which the contents of this configuration ROM was retrieved.


### -field ConfigRom

Receives a pointer to a <b>ConfigRom</b> object.


### -field UnitDirectoryIndex

Receives the index to the node's unit directory in its configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.


### -field UnitDependentDirectoryIndex

Receives the index to the node's unit dependent directory in its configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.


### -field VendorLeafIndex

Receives the index to the node's vendor textual leaf in the configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.


### -field ModelLeafIndex

Receives the index to the node's model textual leaf in the configuration ROM. This is an index to the <b>Entries</b> array in the <b>u.GetConfigRom.ConfigRom</b> structure.

