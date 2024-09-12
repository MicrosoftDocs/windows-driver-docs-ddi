---
UID: NE:srb.STOR_PNP_ACTION
tech.root: storage
title: STOR_PNP_ACTION (srb.h)
ms.date: 03/12/2024
targetos: Windows
description: Enumerates Plug and Play minor function codes.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: srb.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - srb.h
api_name:
 - STOR_PNP_ACTION
 - PSTOR_PNP_ACTION
f1_keywords:
 - STOR_PNP_ACTION
 - srb/STOR_PNP_ACTION
 - PSTOR_PNP_ACTION
 - srb/PSTOR_PNP_ACTION
dev_langs:
 - c++
helpviewer_keywords:
 - STOR_PNP_ACTION
---

## -description

Enumerates Plug and Play minor function codes.

## -enum-fields

### -field StorStartDevice

Sends a request to start the device.

### -field StorRemoveDevice

Sends a request to remove the device.

### -field StorStopDevice

Indicates that the device is stopping.

### -field StorQueryCapabilities

Sends a request to query the capabilities of the device.

### -field StorQueryResourceRequirements

Sends a request to query the resource requirements of the device.

### -field StorFilterResourceRequirements

Sends a request to filter the resource requirements of the device.

### -field StorSurpriseRemoval

Indicates that the device has been removed.

## -remarks

These values are passed in through the PnPAction field of a **[SRBEX_DATA_PNP](ns-srb-_srbex_data_pnp.md)** structure.

## -see-also

- **[SRBEX_DATA_PNP](ns-srb-_srbex_data_pnp.md)**
