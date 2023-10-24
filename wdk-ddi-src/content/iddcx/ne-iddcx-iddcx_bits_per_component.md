---
UID: NE:iddcx.IDDCX_BITS_PER_COMPONENT
tech.root: display
title: IDDCX_BITS_PER_COMPONENT
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_BITS_PER_COMPONENT enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_BITS_PER_COMPONENT
f1_keywords:
 - IDDCX_BITS_PER_COMPONENT
 - iddcx/IDDCX_BITS_PER_COMPONENT
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_BITS_PER_COMPONENT
---

## -description

An **IDDCX_BITS_PER_COMPONENT** enumeration value identifies the supported or requested number of bits per color component for the dithering support of a target.

## -enum-fields

### -field IDDCX_BITS_PER_COMPONENT_NONE:0

A driver can use this flag to indicate no support for a particular wire encoding format; for example, in calls to [**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md) or [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md). When it is used as an input in the driver, for example as part of a call to [**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md), this value is never used.

### -field IDDCX_BITS_PER_COMPONENT_6:0x1

For driver reporting, indicates support for sending color component values using 6 bits. For driver information, indicates 6 bits per component should be sent to the monitor.

### -field IDDCX_BITS_PER_COMPONENT_8:0x2

For driver reporting, indicates support for sending color component values using 8 bits. For driver information, indicates 8 bits per component should be sent to the monitor.

### -field IDDCX_BITS_PER_COMPONENT_10:0x4

For driver reporting, indicates support for sending color component values using 10 bits. For driver information, indicates 10 bits per component should be sent to the monitor.

### -field IDDCX_BITS_PER_COMPONENT_12:0x8

For driver reporting, indicates support for sending color component values using 12 bits. For driver information, indicates 12 bits per component should be sent to the monitor.

### -field IDDCX_BITS_PER_COMPONENT_14:0x10

For driver reporting, indicates support for sending color component values using 14 bits. For driver information, indicates 14 bits per component should be sent to the monitor.

### -field IDDCX_BITS_PER_COMPONENT_16:0x20

For driver reporting, indicates support for sending color component values using 16 bits. For driver information, indicates 16 bits per component should be sent to the monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_QUERY_TARGET_INFO**](nc-iddcx-evt_idd_cx_adapter_query_target_info.md)

[**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md)

[**IDDCX_WIRE_BITS_PER_COMPONENT**](ns-iddcx-iddcx_wire_bits_per_component.md)
