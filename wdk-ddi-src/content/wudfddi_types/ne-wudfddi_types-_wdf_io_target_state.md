---
UID: NE:wudfddi_types._WDF_IO_TARGET_STATE
title: _WDF_IO_TARGET_STATE (wudfddi_types.h)
description: Learn how the WDF_IO_TARGET_STATE enumeration specifies the states that an I/O target can be in.
old-location: wdf\wdf_io_target_state.htm
tech.root: wdf
ms.date: 08/12/2022
keywords: ["WDF_IO_TARGET_STATE enumeration"]
ms.keywords: "*PWDF_IO_TARGET_STATE, DFIOTargetRef_0dbd75b8-eb70-4996-8a13-80fb90f86dca.xml, PWDF_IO_TARGET_STATE, PWDF_IO_TARGET_STATE enumeration pointer, WDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE enumeration, WdfIoTargetClosed, WdfIoTargetClosedForQueryRemove, WdfIoTargetDeleted, WdfIoTargetPurged, WdfIoTargetStarted, WdfIoTargetStateUndefined, WdfIoTargetStopped, _WDF_IO_TARGET_STATE, kmdf.wdf_io_target_state, wdf.wdf_io_target_state, wdfiotarget/PWDF_IO_TARGET_STATE, wdfiotarget/WDF_IO_TARGET_STATE, wdfiotarget/WdfIoTargetClosed, wdfiotarget/WdfIoTargetClosedForQueryRemove, wdfiotarget/WdfIoTargetDeleted, wdfiotarget/WdfIoTargetPurged, wdfiotarget/WdfIoTargetStarted, wdfiotarget/WdfIoTargetStateUndefined, wdfiotarget/WdfIoTargetStopped, wudfddi_types/PWDF_IO_TARGET_STATE, wudfddi_types/WDF_IO_TARGET_STATE, wudfddi_types/WdfIoTargetClosed, wudfddi_types/WdfIoTargetClosedForQueryRemove, wudfddi_types/WdfIoTargetDeleted, wudfddi_types/WdfIoTargetPurged, wudfddi_types/WdfIoTargetStarted, wudfddi_types/WdfIoTargetStateUndefined, wudfddi_types/WdfIoTargetStopped"
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
f1_keywords:
 - _WDF_IO_TARGET_STATE
 - wudfddi_types/_WDF_IO_TARGET_STATE
 - PWDF_IO_TARGET_STATE
 - wudfddi_types/PWDF_IO_TARGET_STATE
 - WDF_IO_TARGET_STATE
 - wudfddi_types/WDF_IO_TARGET_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfiotarget.h
 - wudfddi_types.h
api_name:
 - _WDF_IO_TARGET_STATE
 - PWDF_IO_TARGET_STATE
 - WDF_IO_TARGET_STATE
---

# _WDF_IO_TARGET_STATE enumeration (wudfddi_types.h)

## -description

**[Applies to KMDF and UMDF]**

The **WDF_IO_TARGET_STATE** enumeration specifies the states that an I/O target can be in.

## -enum-fields

### -field WdfIoTargetStateUndefined

Reserved for internal use.

### -field WdfIoTargetStarted

The I/O target is started and can process I/O requests.

### -field WdfIoTargetStopped

The I/O target is temporarily stopped and cannot process I/O requests.

### -field WdfIoTargetClosedForQueryRemove

The I/O target's underlying device might be removed in the near future.

### -field WdfIoTargetClosed

The I/O target is permanently stopped and cannot process I/O requests.

### -field WdfIoTargetDeleted

The I/O target's underlying device has been removed.

### -field WdfIoTargetStateMaximum

## -remarks

To obtain an I/O target's current state, call [WdfIoTargetGetState](../wdfiotarget/nf-wdfiotarget-wdfiotargetgetstate.md).

For more information about states for I/O targets, see [Controlling a General I/O Target's State](/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state).

## -see-also

[WdfIoTargetGetState](../wdfiotarget/nf-wdfiotarget-wdfiotargetgetstate.md)
