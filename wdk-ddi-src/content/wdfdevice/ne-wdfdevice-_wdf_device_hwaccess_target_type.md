---
UID: NE:wdfdevice._WDF_DEVICE_HWACCESS_TARGET_TYPE
title: _WDF_DEVICE_HWACCESS_TARGET_TYPE (wdfdevice.h)
description: Learn how the WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration is used internally by the framework. Do not use. This enumeration is defined in wdfdevice.h.
old-location: wdf\wdf_device_hwaccess_target_size.htm
tech.root: wdf
ms.date: 08/11/2022
keywords: ["WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration"]
ms.keywords: "*PWDF_DEVICE_HWACCESS_TARGET_TYPE, PWDF_DEVICE_HWACCESS_TARGET_TYPE, PWDF_DEVICE_HWACCESS_TARGET_TYPE enumeration pointer, WDF_DEVICE_HWACCESS_TARGET_SIZE, WDF_DEVICE_HWACCESS_TARGET_TYPE, WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration, WdfDeviceHwAccessTargetSizeInvalid, WdfDeviceHwAccessTargetSizeMaximum, WdfDeviceHwAccessTargetSizeUchar, WdfDeviceHwAccessTargetSizeUlong, WdfDeviceHwAccessTargetSizeUlong64, WdfDeviceHwAccessTargetSizeUshort, _WDF_DEVICE_HWACCESS_TARGET_TYPE, umdf.wdf_device_hwaccess_target_size, wdf.wdf_device_hwaccess_target_size, wdfdevice/PWDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WDF_DEVICE_HWACCESS_TARGET_TYPE, wdfdevice/WdfDeviceHwAccessTargetSizeInvalid, wdfdevice/WdfDeviceHwAccessTargetSizeMaximum, wdfdevice/WdfDeviceHwAccessTargetSizeUchar, wdfdevice/WdfDeviceHwAccessTargetSizeUlong, wdfdevice/WdfDeviceHwAccessTargetSizeUlong64, wdfdevice/WdfDeviceHwAccessTargetSizeUshort, wudfddi_types/PWDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/WDF_DEVICE_HWACCESS_TARGET_TYPE, wudfddi_types/WdfDeviceHwAccessTargetSizeInvalid, wudfddi_types/WdfDeviceHwAccessTargetSizeMaximum, wudfddi_types/WdfDeviceHwAccessTargetSizeUchar, wudfddi_types/WdfDeviceHwAccessTargetSizeUlong, wudfddi_types/WdfDeviceHwAccessTargetSizeUlong64, wudfddi_types/WdfDeviceHwAccessTargetSizeUshort"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
req.typenames: WDF_DEVICE_HWACCESS_TARGET_TYPE, *PWDF_DEVICE_HWACCESS_TARGET_TYPE
f1_keywords:
 - _WDF_DEVICE_HWACCESS_TARGET_TYPE
 - wdfdevice/_WDF_DEVICE_HWACCESS_TARGET_TYPE
 - PWDF_DEVICE_HWACCESS_TARGET_TYPE
 - wdfdevice/PWDF_DEVICE_HWACCESS_TARGET_TYPE
 - WDF_DEVICE_HWACCESS_TARGET_TYPE
 - wdfdevice/WDF_DEVICE_HWACCESS_TARGET_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
 - wudfddi_types.h
api_name:
 - _WDF_DEVICE_HWACCESS_TARGET_TYPE
 - PWDF_DEVICE_HWACCESS_TARGET_TYPE
 - WDF_DEVICE_HWACCESS_TARGET_TYPE
---

# _WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration (wdfdevice.h)

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1. All new UMDF drivers should be written using UMDF 2. No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10. Universal Windows drivers must use UMDF 2. For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).

The **WDF_DEVICE_HWACCESS_TARGET_SIZE** enumeration is used internally by the framework. Do not use.

## -enum-fields

### -field WdfDeviceHwAccessTargetTypeInvalid

### -field WdfDeviceHwAccessTargetTypeRegister

### -field WdfDeviceHwAccessTargetTypeRegisterBuffer

### -field WdfDeviceHwAccessTargetTypePort

### -field WdfDeviceHwAccessTargetTypePortBuffer

### -field WdfDeviceHwAccessTargetTypeMaximum

## -see-also

- [UMDF Structures and Enumeration Types](../wudfddi/index.md)