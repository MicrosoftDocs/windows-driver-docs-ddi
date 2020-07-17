---
UID: NE:ntddstor._STORAGE_DIAGNOSTIC_TARGET_TYPE
title: _STORAGE_DIAGNOSTIC_TARGET_TYPE (ntddstor.h)
description: The STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic.
old-location: storage\storage_diagnostic_target_type.htm
tech.root: storage
ms.assetid: 8BC338FB-7C76-49D3-96E5-0F20C4A250CE
ms.date: 03/29/2018
keywords: ["_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration"]
ms.keywords: "*PSTORAGE_DIAGNOSTIC_TARGET_TYPE, PSTORAGE_DIAGNOSTIC_TARGET_TYPE, PSTORAGE_DIAGNOSTIC_TARGET_TYPE enumeration pointer [Storage Devices], STORAGE_DIAGNOSTIC_TARGET_TYPE, STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration [Storage Devices], StorageDiagnosticTargetTypeHbaFirmware, StorageDiagnosticTargetTypeMax, StorageDiagnosticTargetTypeMiniport, StorageDiagnosticTargetTypePort, StorageDiagnosticTargetTypeUndefined, _STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/PSTORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/StorageDiagnosticTargetTypeHbaFirmware, ntddstor/StorageDiagnosticTargetTypeMax, ntddstor/StorageDiagnosticTargetTypeMiniport, ntddstor/StorageDiagnosticTargetTypePort, ntddstor/StorageDiagnosticTargetTypeUndefined, storage.storage_diagnostic_target_type"
f1_keywords:
 - "ntddstor/STORAGE_DIAGNOSTIC_TARGET_TYPE"
 - "STORAGE_DIAGNOSTIC_TARGET_TYPE"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
- ntddstor.h
api_name:
- STORAGE_DIAGNOSTIC_TARGET_TYPE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_TARGET_TYPE, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE
---

# _STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration


## -description


The <b>STORAGE_DIAGNOSTIC_TARGET_TYPE</b> enumeration specifies the target type of a storage diagnostic.


## -enum-fields




### -field StorageDiagnosticTargetTypeUndefined

Specifies the target type is undefined.


### -field StorageDiagnosticTargetTypePort

Specifies the target type is a port driver.


### -field StorageDiagnosticTargetTypeMiniport

Specifies the target type is a Miniport driver.


### -field StorageDiagnosticTargetTypeHbaFirmware

Specifies the target type is a Hba Firmware driver.


### -field StorageDiagnosticTargetTypeMax

Specifies the target type is a Max driver.

