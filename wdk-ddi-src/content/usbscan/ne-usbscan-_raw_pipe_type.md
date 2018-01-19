---
UID: NE:usbscan._RAW_PIPE_TYPE
title: _RAW_PIPE_TYPE
author: windows-driver-content
description: The RAW_PIPE_TYPE data type is used to specify the type of a USB pipe.
old-location: image\raw_pipe_type.htm
old-project: image
ms.assetid: 6af4161c-7caa-4d80-8938-303380ee3058
ms.author: windowsdriverdev
ms.date: 1/17/2018
ms.keywords: _RAW_PIPE_TYPE, RAW_PIPE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RAW_PIPE_TYPE
req.alt-loc: usbscan.h
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
req.typenames: RAW_PIPE_TYPE
req.product: Windows 10 or later.
---

# _RAW_PIPE_TYPE enumeration



## -description
The RAW_PIPE_TYPE data type is used to specify the type of a USB pipe. The values are defined as follows:



## -syntax

````
typedef enum _RAW_PIPE_TYPE { 
  USBSCAN_PIPE_CONTROL      = 0,
  USBSCAN_PIPE_ISOCHRONOUS  = 1,
  USBSCAN_PIPE_BULK         = 2,
  USBSCAN_PIPE_INTERRUPT    = 3
} RAW_PIPE_TYPE;
````


## -enum-fields

### -field USBSCAN_PIPE_CONTROL

Identifies the control pipe.


### -field USBSCAN_PIPE_ISOCHRONOUS

Identifies an isochronous pipe.


### -field USBSCAN_PIPE_BULK

Identifies a bulk IN or bulk OUT pipe.


### -field USBSCAN_PIPE_INTERRUPT

Identifies an interrupt pipe.


## -remarks
