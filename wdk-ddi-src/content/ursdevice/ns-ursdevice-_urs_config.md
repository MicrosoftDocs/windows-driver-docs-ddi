---
UID: NS:ursdevice._URS_CONFIG
title: _URS_CONFIG (ursdevice.h)
description: Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling URS_CONFIG_INIT.
old-location: buses\urs_config.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["URS_CONFIG structure"]
ms.keywords: "*PURS_CONFIG, PURS_CONFIG, PURS_CONFIG structure pointer [Buses], URS_CONFIG, URS_CONFIG structure [Buses], _URS_CONFIG, buses.urs_config, ursdevice/PURS_CONFIG, ursdevice/URS_CONFIG"
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.typenames: URS_CONFIG, *PURS_CONFIG
f1_keywords:
 - _URS_CONFIG
 - ursdevice/_URS_CONFIG
 - PURS_CONFIG
 - ursdevice/PURS_CONFIG
 - URS_CONFIG
 - ursdevice/URS_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ursdevice.h
api_name:
 - _URS_CONFIG
 - PURS_CONFIG
 - URS_CONFIG
---

# _URS_CONFIG structure


## -description

Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>.

## -struct-fields

### -field Size

The size of this structure.

### -field HostInterfaceType

A <a href="/windows-hardware/drivers/ddi/urstypes/ne-urstypes-_urs_host_interface_type">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of USB host controller: EHCI, xHCI, or other.

### -field EvtUrsFilterRemoveResourceRequirements

A pointer to an <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function.

### -field EvtUrsSetRole

A pointer to an <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_set_role">EVT_URS_SET_ROLE</a> callback function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>

