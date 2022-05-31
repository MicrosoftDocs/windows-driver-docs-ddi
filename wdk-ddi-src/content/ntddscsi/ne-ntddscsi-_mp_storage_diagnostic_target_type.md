---
UID: NE:ntddscsi._MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
title: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE (ntddscsi.h)
description: The MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic.
old-location: storage\mp_storage_diagnostic_target_type.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration"]
ms.keywords: "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration [Storage Devices], PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration pointer [Storage Devices], StorageDiagnosticTargetTypeHbaFirmware, StorageDiagnosticTargetTypeMax, StorageDiagnosticTargetTypeMiniport, StorageDiagnosticTargetTypePort, StorageDiagnosticTargetTypeUndefined, _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddscsi/MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddscsi/PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddscsi/StorageDiagnosticTargetTypeHbaFirmware, ntddscsi/StorageDiagnosticTargetTypeMax, ntddscsi/StorageDiagnosticTargetTypeMiniport, ntddscsi/StorageDiagnosticTargetTypePort, ntddscsi/StorageDiagnosticTargetTypeUndefined, storage.mp_storage_diagnostic_target_type"
req.header: ntddscsi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
f1_keywords:
 - _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - ntddscsi/_MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - ntddscsi/PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - ntddscsi/MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
 - MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration

## -description

The **MP_STORAGE_DIAGNOSTIC_TARGET_TYPE** enumeration specifies the target type of a storage diagnostic.

## -enum-fields

### -field MpStorageDiagnosticTargetTypeUndefined:0

The diagnostic target is undefined.

### -field MpStorageDiagnosticTargetTypeMiniport:2

The diagnostic target is a miniport driver.

### -field MpStorageDiagnosticTargetTypeHbaFirmware

The diagnostic target is an Hba Firmware driver.

### -field MpStorageDiagnosticTargetTypeMax

Maximum allowed value for this enumeration.
