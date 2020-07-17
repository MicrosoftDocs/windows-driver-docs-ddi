---
UID: NE:dispmprt._DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
title: DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
description: DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY provides basic display topology information to the operating system (OS) when it is gathering nonintrusive display diagnostic information.
tech.root: display
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
 - DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
f1_keywords:
 - dispmprt/_DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
 - dispmprt/DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY
 - ""
dev_langs:
 - c++
---

# DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY enumeration

## -description

**DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY** provides basic display topology information to the operating system (OS) when it is gathering nonintrusive display diagnostic information.

## -enum-fields

### -field DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY_UNINITIALIZED

Reserved for OS use during diagnostic initialization.

### -field DXGK_DIAG_DISPLAY_CONNECTED_DIRECTLY

The monitor is connected directly to the graphics card.

### -field DXGK_DIAG_DISPLAY_CONNECTED_INDIRECTLY_CONVERTOR

The monitor is connected indirectly to the graphics card via a convertor/connector. In most cases, the driver can only detect active convertors.

### -field DXGK_DIAG_DISPLAY_CONNECTED_INDIRECTLY_HUB

The monitor is connected indirectly to the graphics card via a hub.

### -field DXGK_DIAG_DISPLAY_CONNECTED_INDIRECTLY

The monitor is connected indirectly to the graphics card but the driver cannot determine whether it is connected via a hub or a convertor.

### -field DXGK_DIAG_DISPLAY_CONNECTED_UNKNOWN

The driver cannot determine whether the monitor is connected directly or indirectly to the graphics card. This value should be used rarely, such as in cases where the connector is a pass through.

## -remarks

The **DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY** enumeration is a member of the [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure. It is used while gathering display diagnostic information via calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md).

Dongles and hubs can increase the failure points that can occur during monitor enumeration and negotiations. The operating system (OS) can use the value of **DXGK_DIAG_BASIC_DISPLAY_TOPOLOGY** to determine whether to collect more detailed topology information, if available (for example using the DP AUX DDIs), to determine the current state of the hub and/or dongles to look for the culprit component.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DXGKARG_GETDISPLAYSTATENONINTRUSIVE**](ns-dispmprt-dxgkarg_getdisplaystatenonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

[**DXGKDDI_DPAUXIOTRANSMISSION**](nc-dispmprt-dxgkddi_dpauxiotransmission.md)
