---
UID: NE:sddef.SD_TRANSFER_DIRECTION
tech.root: SD
title: SD_TRANSFER_DIRECTION
ms.date: 12/16/2021
targetos: Windows
description: Learn more about the SD_TRANSFER_DIRECTION enumerator.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: sddef.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sddef.h
api_name:
 - SD_TRANSFER_DIRECTION
f1_keywords:
 - SD_TRANSFER_DIRECTION
 - sddef/SD_TRANSFER_DIRECTION
dev_langs:
 - c++
helpviewer_keywords:
 - SD_TRANSFER_DIRECTION
---

## -description

A **SD_TRANSFER_DIRECTION** value indicates the data transfer direction of a Secure Digital (SD) card command.

## -enum-fields

### -field SDTD_UNSPECIFIED

The data transfer direction is unspecified.

### -field SDTD_READ

The data transfer is from the SD device to the host.

### -field SDTD_WRITE

The data transfer is from the SD host to the device.

## -see-also

[**SDCMD_DESCRIPTOR**](ns-sddef-_sdcmd_descriptor.md)

