---
UID: NS:ntddk.HAL_DISPATCH
tech.root: kernel
title: HAL_DISPATCH (ntddk.h)
ms.date: 04/17/2023
targetos: Windows
description: This topic describes the HAL_DISPATCH structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: HAL_DISPATCH, *PHAL_DISPATCH
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PHAL_DISPATCH
 - HAL_DISPATCH
f1_keywords:
 - PHAL_DISPATCH
 - ntddk/PHAL_DISPATCH
 - HAL_DISPATCH
 - ntddk/HAL_DISPATCH
dev_langs:
 - c++
helpviewer_keywords:
 - HAL_DISPATCH
---

## -description

This topic describes the **HAL_DISPATCH** structure.

## -struct-fields

### -field Version

Defines the **ULONG** member **Version**.

### -field HalQuerySystemInformation

Defines the **pHalQuerySystemInformation** member **HalQuerySystemInformation**.

### -field HalSetSystemInformation

Defines the **pHalSetSystemInformation** member **HalSetSystemInformation**.

### -field HalQueryBusSlots

Defines the **pHalQueryBusSlots** member **HalQueryBusSlots**.

### -field Spare1

Defines the **ULONG** member **Spare1**.

### -field HalExamineMBR

Defines the **pHalExamineMBR** member **HalExamineMBR**.

### -field HalIoReadPartitionTable

Defines the **pHalIoReadPartitionTable** member **HalIoReadPartitionTable**.

### -field HalIoSetPartitionInformation

Defines the **pHalIoSetPartitionInformation** member **HalIoSetPartitionInformation**.

### -field HalIoWritePartitionTable

Defines the **pHalIoWritePartitionTable** member **HalIoWritePartitionTable**.

### -field HalReferenceHandlerForBus

Defines the **pHalReferenceHandlerForBus** member **HalReferenceHandlerForBus**.

### -field HalReferenceBusHandler

Defines the **pHalReferenceBusHandler** member **HalReferenceBusHandler**.

### -field HalDereferenceBusHandler

Defines the **pHalDereferenceBusHandler** member **HalDereferenceBusHandler**.

### -field HalInitPnpDriver

Defines the **pHalInitPnpDriver** member **HalInitPnpDriver**.

### -field HalInitPowerManagement

Defines the **pHalInitPowerManagement** member **HalInitPowerManagement**.

### -field HalGetDmaAdapter

Defines the **pHalGetDmaAdapter** member **HalGetDmaAdapter**.

### -field HalGetInterruptTranslator

Defines the **pHalGetDmaAdapter** member **HalGetInterruptTranslator**.

### -field HalStartMirroring

Defines the **pHalStartMirroring** member **HalStartMirroring**.

### -field HalEndMirroring

Defines the **pHalEndMirroring** member **HalEndMirroring**.

### -field HalMirrorPhysicalMemory

Defines the **pHalMirrorPhysicalMemory** member **HalMirrorPhysicalMemory**.

### -field HalEndOfBoot

Defines the **pHalEndOfBoot** member **HalEndOfBoot**.

### -field HalMirrorVerify

Defines the **pHalMirrorVerify** member **HalMirrorVerify**.

### -field HalGetCachedAcpiTable

Defines the **pHalGetCachedAcpiTable** member **HalGetCachedAcpiTable**.

### -field HalSetPciErrorHandlerCallback

Defines the **pHalSetPciErrorHandlerCallback** member **HalSetPciErrorHandlerCallback**.

### -field HalGetPrmCache

Defines the **pHalGetPrmCache** member **HalGetPrmCache**.

## -remarks

## -see-also
