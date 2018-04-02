---
UID: NS:d4drvif._DOT4_DRIVER_CMD
title: "_DOT4_DRIVER_CMD"
author: windows-driver-content
description: This topic describes the DOT4_DRIVER_CMD structure.
old-location: print\dot4_driver_cmd.htm
old-project: print
ms.assetid: 7F099F7E-6E1F-499A-AF09-80B20429B892
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDOT4_DRIVER_CMD, DOT4_DRIVER_CMD, DOT4_DRIVER_CMD structure [Print Devices], PDOT4_DRIVER_CMD, PDOT4_DRIVER_CMD structure pointer [Print Devices], _DOT4_DRIVER_CMD, d4drvif/DOT4_DRIVER_CMD, d4drvif/PDOT4_DRIVER_CMD, print.dot4_driver_cmd"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D4drvif.h
api_name:
-	DOT4_DRIVER_CMD
product:
- Windows
targetos: Windows
req.typenames: DOT4_DRIVER_CMD, *PDOT4_DRIVER_CMD
---

# _DOT4_DRIVER_CMD structure


## -description


This topic describes the <b>DOT4_DRIVER_CMD</b> structure.


## -struct-fields




### -field hChannelHandle

Specifies the handle to the channel.


### -field ulSize

Specifies the length of the request.


### -field ulOffset

Specifies the offset into the  buffer.


### -field ulTimeout

Specifies the timeout of the operation. Can be INFINITE.

