---
UID: NS:wiadef._WIA_MICR_INFO
title: _WIA_MICR_INFO (wiadef.h)
description: The WIA_MICR_INFO structure stores information for one decoded MICR code.
old-location: image\wia_micr_info.htm
tech.root: image
ms.assetid: E91F5D6F-40F9-4CE2-8C51-4CA7FB27F2C3
ms.date: 05/03/2018
keywords: ["WIA_MICR_INFO structure"]
ms.keywords: WIA_MICR_INFO, WIA_MICR_INFO structure [Imaging Devices], _WIA_MICR_INFO, image.wia_micr_info, wiadef/WIA_MICR_INFO
f1_keywords:
 - "wiadef/WIA_MICR_INFO"
 - "WIA_MICR_INFO"
req.header: wiadef.h
req.include-header: Wiadef.h
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
- wiadef.h
api_name:
- WIA_MICR_INFO
targetos: Windows
req.typenames: WIA_MICR_INFO
---

# _WIA_MICR_INFO structure


## -description


The <b>WIA_MICR_INFO</b> structure stores information for one decoded MICR code.


## -struct-fields




### -field Size

The total size of this structure, in bytes.


### -field Page

The page number where the MICR code was detected. A zero-based index referring to the current scan job.


### -field Length

Length of the MICR text, in characters, excluding the length of the NULL terminator.


### -field Text

Placeholder for a NULL terminated character string containing the MICR text.

