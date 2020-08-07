---
UID: NE:dispmprt._DXGK_EVENT_TYPE
title: _DXGK_EVENT_TYPE (dispmprt.h)
description: The DXGK_EVENT_TYPE enumeration indicates the event type in a call to the display miniport driver's DxgkDdiNotifyAcpiEvent function.
old-location: display\dxgk_event_type.htm
tech.root: display
ms.assetid: df28ae8f-01f7-42c5-99df-2a3fc7401173
ms.date: 04/16/2018
keywords: ["DXGK_EVENT_TYPE enumeration"]
ms.keywords: "*PDXGK_EVENT_TYPE, DXGK_EVENT_TYPE, DXGK_EVENT_TYPE enumeration [Display Devices], DmEnums_94bee105-be3f-4268-982e-be8581bb9bc0.xml, DxgkAcpiEvent, DxgkDockingEvent, DxgkPowerStateEvent, DxgkUndefinedEvent, IN_DXGK_EVENT_TYPE, PDXGK_EVENT_TYPE, PDXGK_EVENT_TYPE enumeration pointer [Display Devices], _DXGK_EVENT_TYPE, display.dxgk_event_type, dispmprt/DXGK_EVENT_TYPE, dispmprt/DxgkAcpiEvent, dispmprt/DxgkDockingEvent, dispmprt/DxgkPowerStateEvent, dispmprt/DxgkUndefinedEvent, dispmprt/PDXGK_EVENT_TYPE"
f1_keywords:
 - "dispmprt/DXGK_EVENT_TYPE"
 - "DXGK_EVENT_TYPE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_EVENT_TYPE
targetos: Windows
req.typenames: DXGK_EVENT_TYPE, *PDXGK_EVENT_TYPE
---

# _DXGK_EVENT_TYPE enumeration


## -description


The DXGK_EVENT_TYPE enumeration indicates the event type in a call to the display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_notify_acpi_event">DxgkDdiNotifyAcpiEvent</a> function.


## -enum-fields




### -field DxgkUndefinedEvent

Indicates that a variable of type DXGK_EVENT_TYPE has not yet been assigned a meaningful value.


### -field DxgkAcpiEvent

Indicates that the event is an ACPI event.


### -field DxgkPowerStateEvent

Indicates that the event is a power state event.


### -field DxgkDockingEvent

Indicates that the event is a docking event.


### -field DxgkChainedAcpiEvent

Indicates that the ACPI event was sent to the integrated adapter but has been redirected to the driver for the discrete adapter.

Supported by WDDM 2.1 and later drivers.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_notify_acpi_event">DxgkDdiNotifyAcpiEvent</a>
 

 

