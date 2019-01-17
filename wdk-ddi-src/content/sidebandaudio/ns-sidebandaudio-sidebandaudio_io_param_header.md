---
UID: NS:sidebandaudio.__unnamed_union_0
title: SIDEBANDAUDIO_IO_PARAM_HEADER
description: Describes the size and type of parameter.
ms.assetid: e2f0fc99-4a73-44de-97f3-24f3a3d13b18
ms.date: 09/07/2018
ms.topic: struct
ms.keywords: SIDEBANDAUDIO_IO_PARAM_HEADER, SIDEBANDAUDIO_IO_PARAM_HEADER, *PSIDEBANDAUDIO_IO_PARAM_HEADER, 
req.header: sidebandaudio.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: SIDEBANDAUDIO_IO_PARAM_HEADER, *PSIDEBANDAUDIO_IO_PARAM_HEADER
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	sidebandaudio.h
api_name: 
-	SIDEBANDAUDIO_IO_PARAM_HEADER
product: Windows
targetos: Windows
tech.root: audio
ms.custom: RS5
---

# SIDEBANDAUDIO_IO_PARAM_HEADER structure

## -description

Describes the size and type of parameter.


## -struct-fields

### -field ParamSet
Parameter Set - This could be Microsoft Standard set or IHV defined.
 
### -field TypeId
Type of parameter.
 
### -field Size
Size in bytes of Parameter. In case of IOCTL_SBAUD_GET_SIOPxxx Size will indicate size of any extra input parameter.

### -field Alignment
TBD 

## -remarks

## -see-also
[sidebandaudio.h](index.md)
