---
UID: NS:ntddk._WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
title: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
description: 
tech.root: whea
ms.date: 04/01/2020
keywords: ["WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER structure"]
ms.keywords: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, *PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER,
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER, *PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
targetos: Windows
f1_keywords:
 - _WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - ntddk/_WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - ntddk/PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - ntddk/WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - PWHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
 - WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER
product:
 - Windows
---

# WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER structure


## -description

## -struct-fields

### -field Version

A ULONG specifying the version of this structure to use. Starting in Windows 10, version 2004, set to `WHEA_DEVICE_DRIVER_CONFIG_V2`.

### -field SourceGuid

A GUID corresponding to the driver generating the errors.

### -field LogTag

Used by device drivers that also create [SEL (System Event Log)](/windows-hardware/drivers/whea/querying-the-system-event-log-for-hardware-error-events) data to help identify the source of the SEL log.

### -field Reserved

Reserved for system use.

### -field Initialize

A pointer to the driver's [*WHEA_ERROR_SOURCE_INITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_initialize_device_driver.md) event callback function.

### -field Uninitialize

A pointer to the driver's [*WHEA_ERROR_SOURCE_UNINITIALIZE_DEVICE_DRIVER*](nc-ntddk-_whea_error_source_uninitialize_device_driver.md) event callback function.

### -field MaxSectionDataLength

Specifies the maximum size, in bytes, for a single section in a reported error.

### -field MaxSectionsPerReport

A ULONG that specifies the maximum number of sections per report.

### -field CreatorId

A GUID identifying the creator, i.e. the organization, that is generating the error.

### -field PartitionId

A GUID that is used in the [Common Platform Error Record (CPER)](/windows-hardware/drivers/whea/error-records). Can be zero.

## -remarks

The WHEA_ERROR_SOURCE_CONFIGURATION_DEVICE_DRIVER structure is used as input to the [**WheaAddErrorSourceDeviceDriver**](nf-ntddk-wheaadderrorsourcedevicedriver.md) function.

For more info, see [Using WHEA on Windows 10](/windows-hardware/drivers/whea/using-whea-on-windows-10).

## -see-also

