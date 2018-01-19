---
UID: NE:oemrilapitypes.RIL_DEVSPECIFIC_CMD
title: RIL_DEVSPECIFIC_CMD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_devspecific_cmd.htm
old-project: netvista
ms.assetid: 5c6ac937-c5ff-4788-9c54-375f364bd823
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_DEVSPECIFIC_CMD, RIL_DEVSPECIFIC_CMD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: oemrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RIL_DEVSPECIFIC_CMD
req.alt-loc: oemrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: RIL_DEVSPECIFIC_CMD
---

# RIL_DEVSPECIFIC_CMD enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RIL_DEVSPECIFIC_CMD { 
  RIL_DEVSPECIFIC_CMD_OEM_GBA_UNKNOWN,
  RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_CAPABLE,
  RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_TOKEN,
  RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_TOKEN_FORCE,
  RIL_DEVSPECIFIC_CMD_OEM_MAX
} RIL_DEVSPECIFIC_CMD;
````


## -enum-fields

### -field RIL_DEVSPECIFIC_CMD_OEM_GBA_UNKNOWN


### -field RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_CAPABLE


### -field RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_TOKEN


### -field RIL_DEVSPECIFIC_CMD_OEM_GBA_GET_GBA_TOKEN_FORCE


### -field RIL_DEVSPECIFIC_CMD_OEM_MAX


## -remarks
