---
UID: NE:ntddstor._STORAGE_DIAGNOSTIC_TARGET_TYPE
title: "_STORAGE_DIAGNOSTIC_TARGET_TYPE"
author: windows-driver-content
description: The STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration specifies the target type of a storage diagnostic.
old-location: storage\storage_diagnostic_target_type.htm
old-project: storage
ms.assetid: 8BC338FB-7C76-49D3-96E5-0F20C4A250CE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddstor/StorageDiagnosticTargetTypeHbaFirmware, _STORAGE_DIAGNOSTIC_TARGET_TYPE, STORAGE_DIAGNOSTIC_TARGET_TYPE, StorageDiagnosticTargetTypePort, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/StorageDiagnosticTargetTypeUndefined, ntddstor/StorageDiagnosticTargetTypePort, ntddstor/StorageDiagnosticTargetTypeMiniport, ntddstor/StorageDiagnosticTargetTypeMax, StorageDiagnosticTargetTypeHbaFirmware, storage.storage_diagnostic_target_type, PSTORAGE_DIAGNOSTIC_TARGET_TYPE, StorageDiagnosticTargetTypeUndefined, StorageDiagnosticTargetTypeMiniport, ntddstor/STORAGE_DIAGNOSTIC_TARGET_TYPE, ntddstor/PSTORAGE_DIAGNOSTIC_TARGET_TYPE, STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration [Storage Devices], PSTORAGE_DIAGNOSTIC_TARGET_TYPE enumeration pointer [Storage Devices], StorageDiagnosticTargetTypeMax
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_DIAGNOSTIC_TARGET_TYPE
product: Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_TARGET_TYPE, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE
---

# _STORAGE_DIAGNOSTIC_TARGET_TYPE enumeration


## -description


The <b>STORAGE_DIAGNOSTIC_TARGET_TYPE</b> enumeration specifies the target type of a storage diagnostic.


## -syntax


````
typedef enum _STORAGE_DIAGNOSTIC_TARGET_TYPE { 
  StorageDiagnosticTargetTypeUndefined    = 0,
  StorageDiagnosticTargetTypePort,
  StorageDiagnosticTargetTypeMiniport,
  StorageDiagnosticTargetTypeHbaFirmware,
  StorageDiagnosticTargetTypeMax
} STORAGE_DIAGNOSTIC_TARGET_TYPE, *PSTORAGE_DIAGNOSTIC_TARGET_TYPE;
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

