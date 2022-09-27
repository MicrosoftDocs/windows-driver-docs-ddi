---
UID: NS:ntddmmc._FEATURE_DATA_REMOVABLE_MEDIUM
title: FEATURE_DATA_REMOVABLE_MEDIUM (ntddmmc.h)
description: The FEATURE_DATA_REMOVABLE_MEDIUM structure contains data for the removable medium feature.
old-location: storage\feature_data_removable_medium.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["FEATURE_DATA_REMOVABLE_MEDIUM structure"]
ms.keywords: "*PFEATURE_DATA_REMOVABLE_MEDIUM, FEATURE_DATA_REMOVABLE_MEDIUM, FEATURE_DATA_REMOVABLE_MEDIUM structure [Storage Devices], PFEATURE_DATA_REMOVABLE_MEDIUM, PFEATURE_DATA_REMOVABLE_MEDIUM structure pointer [Storage Devices], _FEATURE_DATA_REMOVABLE_MEDIUM, ntddmmc/FEATURE_DATA_REMOVABLE_MEDIUM, ntddmmc/PFEATURE_DATA_REMOVABLE_MEDIUM, storage.feature_data_removable_medium, structs-CD-ROM_f9ce701e-11b7-478e-969e-c2744477d348.xml"
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
targetos: Windows
req.typenames: FEATURE_DATA_REMOVABLE_MEDIUM, *PFEATURE_DATA_REMOVABLE_MEDIUM
f1_keywords:
 - _FEATURE_DATA_REMOVABLE_MEDIUM
 - ntddmmc/_FEATURE_DATA_REMOVABLE_MEDIUM
 - PFEATURE_DATA_REMOVABLE_MEDIUM
 - ntddmmc/PFEATURE_DATA_REMOVABLE_MEDIUM
 - FEATURE_DATA_REMOVABLE_MEDIUM
 - ntddmmc/FEATURE_DATA_REMOVABLE_MEDIUM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddmmc.h
api_name:
 - _FEATURE_DATA_REMOVABLE_MEDIUM
 - PFEATURE_DATA_REMOVABLE_MEDIUM
 - FEATURE_DATA_REMOVABLE_MEDIUM
---

# FEATURE_DATA_REMOVABLE_MEDIUM structure

## -description

The **FEATURE_DATA_REMOVABLE_MEDIUM** structure contains data for the removable medium feature.

## -struct-fields

### -field Header

Contains a [**FEATURE_HEADER**](ns-ntddmmc-_feature_header.md) structure with header information for this feature descriptor.

### -field Lockable

Indicates, when set to 1, that the initiator can lock the medium into the device. When set to zero, this bit indicates that the medium cannot be locked into the device.

### -field DBML

### -field DefaultToPrevent

Indicates, when set to zero, that the prevent jumper is present. This overrides the lock command, so that locking the device shall not prevent the insertion of media.

### -field Eject

Indicates, when set to 1, that the device can eject the medium or magazine. When set to zero, this bit indicates that the device cannot eject the medium or magazine by means of the normal start/stop command sequence.

### -field Load

### -field LoadingMechanism

Indicates the type of loading mechanism. See the *SCSI Multimedia - 4 (MMC-4)* specification for the list of values that this member can take.

### -field Reserved3[3]

Reserved.

## -remarks

This structure holds data for the feature named "Removable Medium" by the *MMC-3* specification. Devices that support this feature allow the medium to be removed from the device. They also can communicate to the initiator that the user wants to eject the medium or has inserted a new medium.

## -see-also

[**FEATURE_HEADER**](ns-ntddmmc-_feature_header.md)

[**FEATURE_NUMBER**](ne-ntddmmc-_feature_number.md)
