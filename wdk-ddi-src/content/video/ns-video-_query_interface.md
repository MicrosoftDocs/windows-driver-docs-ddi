---
UID: NS:video._QUERY_INTERFACE
title: QUERY_INTERFACE (video.h)
description: Learn more about the QUERY_INTERFACE structure.
tech.root: display
ms.date: 01/13/2025
req.header: video.h
req.include-header: Video.h
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
req.typenames: QUERY_INTERFACE, *PQUERY_INTERFACE
f1_keywords:
 - _QUERY_INTERFACE
 - video/_QUERY_INTERFACE
 - PQUERY_INTERFACE
 - video/PQUERY_INTERFACE
 - QUERY_INTERFACE
 - video/QUERY_INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - video.h
api_name:
 - _QUERY_INTERFACE
 - PQUERY_INTERFACE
 - QUERY_INTERFACE
---

# QUERY_INTERFACE structure

## -description

The **QUERY_INTERFACE** structure describes the interface being requested.

## -struct-fields

### -field InterfaceType

Pointer to a GUID that identifies the interface being requested. If the kernel-mode display miniport driver (KMD) (or [legacy video miniport driver](/previous-versions/windows/drivers/display/video-miniport-driver-within-the-graphics-architecture--windows-2000-m)) doesn't support the specified **InterfaceType**, it should fail the call and return immediately.

The parent generates this GUID with *uuidgen.exe*. See [Defining and Exporting New GUIDs](/windows-hardware/drivers/kernel/defining-and-exporting-new-guids) for details.

### -field Size

Specifies the size in bytes of the [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure to which **Interface** points. The driver must not return an **INTERFACE** structure larger than **Size** bytes.

### -field Version

Specifies the version of the interface being requested.

If a parent supports more than one version of an interface, its driver should return the specified version or, if possible, the closest supported version without exceeding the requested version. The caller is responsible for examining the returned **Version** and determine what to do based on that value.

### -field Interface

Pointer to an [**INTERFACE**](../wdm/ns-wdm-_interface.md) structure in which the driver returns the requested interface information. The caller is responsible for allocating this structure before calling [**DxgkddiQueryInterface**](../dispmprt/nc-dispmprt-dxgkddi_query_interface.md) (or [**HwVidQueryInterface**](nc-video-pvideo_hw_query_interface.md)).

### -field InterfaceSpecificData

Specifies additional information about the interface being requested. Typically, this member is NULL, and the **InterfaceType** and **Version** members are sufficient for the parent to identify the interface being requested.

### -field DeviceUid

A positive integer that identifies the device for which the interface is being queried. If **DeviceUid** is equal to DISPLAY_ADAPTER_HW_ID (defined in *Video.h*), the device is the display adapter itself. Otherwise, **DeviceUid** is the identifier of a child device of the display adapter. Child device identifiers were previously assigned by the [**DxgkDdiQueryChildRelations**](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md) function. Available starting with Windows 8.1 (WDDM 1.3).

## -remarks

The **QueryInterface** parameter of the KMD's [**DxgkddiQueryInterface**](../dispmprt/nc-dispmprt-dxgkddi_query_interface.md) callback (or [legacy video miniport driver](/previous-versions/windows/drivers/display/video-miniport-driver-within-the-graphics-architecture--windows-2000-m)'s [**HwVidQueryInterface**](nc-video-pvideo_hw_query_interface.md) function) is a pointer to a **QUERY_INTERFACE** structure.

## -see-also

[**DxgkddiQueryInterface**](../dispmprt/nc-dispmprt-dxgkddi_query_interface.md)

[**HwVidQueryInterface**](nc-video-pvideo_hw_query_interface.md)
