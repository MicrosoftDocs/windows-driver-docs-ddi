---
UID: NS:wdm.ACPI_INTERFACE_STANDARD2
tech.root: kernel
title: ACPI_INTERFACE_STANDARD2 (wdm.h)
ms.date: 03/10/2022
targetos: Windows
description: This topic describes the ACPI_INTERFACE_STANDARD2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACPI_INTERFACE_STANDARD2, *PACPI_INTERFACE_STANDARD2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PACPI_INTERFACE_STANDARD2
 - ACPI_INTERFACE_STANDARD2
f1_keywords:
 - PACPI_INTERFACE_STANDARD2
 - wdm/PACPI_INTERFACE_STANDARD2
 - ACPI_INTERFACE_STANDARD2
 - wdm/ACPI_INTERFACE_STANDARD2
dev_langs:
 - c++
helpviewer_keywords:
 - __unnamed_struct_12
---

## -description

This topic describes the **ACPI_INTERFACE_STANDARD2** structure.

## -struct-fields

### -field Size

Describes the **USHORT** member **Size**.

### -field Version

Describes the **USHORT** member **Version**.

### -field Context

Describes the **PVOID** member **Context**.

### -field InterfaceReference

Describes the **PINTERFACE_REFERENCE** member **InterfaceReference**.

### -field InterfaceDereference

Describes the **PINTERFACE_DEREFERENCE** member **InterfaceDereference**.

### -field GpeConnectVector

Describes the **PGPE_CONNECT_VECTOR** member **GpeConnectVector**.

### -field GpeDisconnectVector

Describes the **PGPE_DISCONNECT_VECTOR** member **GpeDisconnectVector**.

### -field GpeEnableEvent

Describes the **PGPE_ENABLE_EVENT** member **GpeEnableEvent**.

### -field GpeDisableEvent

Describes the **PGPE_DISABLE_EVENT** member **GpeDisableEvent**.

### -field GpeClearStatus

Describes the **PGPE_CLEAR_STATUS** member **GpeClearStatus**.

### -field RegisterForDeviceNotifications

Describes the **PREGISTER_FOR_DEVICE_NOTIFICATIONS** member **RegisterForDeviceNotifications**.

### -field UnregisterForDeviceNotifications

Describes the **PUNREGISTER_FOR_DEVICE_NOTIFICATIONS** member **UnregisterForDeviceNotifications**.

## -remarks

## -see-also

