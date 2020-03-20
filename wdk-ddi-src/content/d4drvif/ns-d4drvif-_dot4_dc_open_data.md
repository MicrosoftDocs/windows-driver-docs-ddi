---
UID: NS:d4drvif._DOT4_DC_OPEN_DATA
title: _DOT4_DC_OPEN_DATA (d4drvif.h)
description: This topic describes the DOT4_DC_OPEN_DATA structure.
old-location: print\dot4_dc_open_data.htm
tech.root: print
ms.assetid: 72AE7A78-C02D-4C14-B017-9CEECF34FEDF
ms.date: 04/20/2018
keywords: ["_DOT4_DC_OPEN_DATA structure"]
ms.keywords: "*PDOT4_DC_OPEN_DATA, DOT4_DC_OPEN_DATA, DOT4_DC_OPEN_DATA structure [Print Devices], PDOT4_DC_OPEN_DATA, PDOT4_DC_OPEN_DATA structure pointer [Print Devices], _DOT4_DC_OPEN_DATA, d4drvif/DOT4_DC_OPEN_DATA, d4drvif/PDOT4_DC_OPEN_DATA, print.dot4_dc_open_data"
f1_keywords:
 - "d4drvif/DOT4_DC_OPEN_DATA"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D4drvif.h
api_name:
- DOT4_DC_OPEN_DATA
product:
- Windows
targetos: Windows
req.typenames: DOT4_DC_OPEN_DATA, *PDOT4_DC_OPEN_DATA
---

# _DOT4_DC_OPEN_DATA structure


## -description


This topic describes the <b>DOT4_DC_OPEN_DATA</b> structure.


## -struct-fields




### -field bHsid

Specifies the host socket created by CREATE_SOCKET.


### -field fAddActivity

 


### -field hChannelHandle

Specifies the handle to the channel returned.


#### - unsigned char

Specify TRUE to immediately add activity broadcast upon creation.

