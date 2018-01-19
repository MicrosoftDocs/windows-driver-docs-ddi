---
UID: NS:d4drvif._DOT4_DC_DESTROY_DATA
title: _DOT4_DC_DESTROY_DATA
author: windows-driver-content
description: This topic describes the DOT4_DC_DESTROY_DATA structure.
old-location: print\dot4_dc_destroy_data.htm
old-project: print
ms.assetid: 1AA00E3C-C6FB-49A4-9EFB-DFFEEFF4C0A0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DOT4_DC_DESTROY_DATA, DOT4_DC_DESTROY_DATA, *PDOT4_DC_DESTROY_DATA
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
req.alt-api: DOT4_DC_DESTROY_DATA
req.alt-loc: D4drvif.h
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
req.typenames: DOT4_DC_DESTROY_DATA, *PDOT4_DC_DESTROY_DATA
---

# _DOT4_DC_DESTROY_DATA structure



## -description
This topic describes the <b>DOT4_DC_DESTROY_DATA</b> structure.



## -syntax

````
typedef struct _DOT4_DC_DESTROY_DATA {
  unsigned char bHsid;
} DOT4_DC_DESTROY_DATA, *PDOT4_DC_DESTROY_DATA;
````


## -struct-fields

### -field bHsid

Specifies the host socket created by CREATE_SOCKET.


## -remarks
