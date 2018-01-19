---
UID: NE:ntddscsi._MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
title: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
author: windows-driver-content
description: The MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic.
old-location: storage\mp_storage_diagnostic_target_type.htm
old-project: storage
ms.assetid: 1A48FC0F-7ED2-4F9F-8B61-A498B0D13FE8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddscsi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
req.alt-loc: ntddscsi.h
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
req.typenames: *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration



## -description
The <b>MP_STORAGE_DIAGNOSTIC_TARGET_TYPE</b> enumeration specifies the target type of a storage diagnostic.



## -syntax

````
typedef enum _MP_STORAGE_DIAGNOSTIC_TARGET_TYPE { 
  StorageDiagnosticTargetTypeUndefined    = 0,
  StorageDiagnosticTargetTypePort         = 2,
  StorageDiagnosticTargetTypeMiniport,
  StorageDiagnosticTargetTypeHbaFirmware,
  StorageDiagnosticTargetTypeMax
} MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE;
````


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


## -remarks
