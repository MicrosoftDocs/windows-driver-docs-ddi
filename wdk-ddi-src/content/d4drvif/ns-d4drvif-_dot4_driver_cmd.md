---
UID: NS:d4drvif._DOT4_DRIVER_CMD
title: "_DOT4_DRIVER_CMD"
author: windows-driver-content
description: This topic describes the DOT4_DRIVER_CMD structure.
old-location: print\dot4_driver_cmd.htm
old-project: print
ms.assetid: 7F099F7E-6E1F-499A-AF09-80B20429B892
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: DOT4_DRIVER_CMD structure [Print Devices], PDOT4_DRIVER_CMD, PDOT4_DRIVER_CMD structure pointer [Print Devices], d4drvif/PDOT4_DRIVER_CMD, *PDOT4_DRIVER_CMD, print.dot4_driver_cmd, _DOT4_DRIVER_CMD, DOT4_DRIVER_CMD, d4drvif/DOT4_DRIVER_CMD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d4drvif.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D4drvif.h
apiname:
-	DOT4_DRIVER_CMD
product: Windows
targetos: Windows
req.typenames: "*PDOT4_DRIVER_CMD, DOT4_DRIVER_CMD"
---

# _DOT4_DRIVER_CMD structure


## -description


This topic describes the <b>DOT4_DRIVER_CMD</b> structure.


## -syntax


````
typedef struct _DOT4_DRIVER_CMD {
  CHANNEL_HANDLE hChannelHandle;
  ULONG          ulSize;
  ULONG          ulOffset;
  ULONG          ulTimeout;
} DOT4_DRIVER_CMD, *PDOT4_DRIVER_CMD;
````


## -struct-fields




### -field hChannelHandle

Specifies the handle to the channel.


### -field ulSize

Specifies the length of the request.


### -field ulOffset

Specifies the offset into the  buffer.


### -field ulTimeout

Specifies the timeout of the operation. Can be INFINITE.

