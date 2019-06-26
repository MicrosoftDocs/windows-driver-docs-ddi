---
UID: NS:ursdevice._URS_CONFIG
title: _URS_CONFIG (ursdevice.h)
description: Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling URS_CONFIG_INIT.
old-location: buses\urs_config.htm
tech.root: usbref
ms.assetid: 3857CA53-6992-410A-96D1-EEA9CC586EDF
ms.date: 05/07/2018
ms.keywords: "*PURS_CONFIG, PURS_CONFIG, PURS_CONFIG structure pointer [Buses], URS_CONFIG, URS_CONFIG structure [Buses], _URS_CONFIG, buses.urs_config, ursdevice/PURS_CONFIG, ursdevice/URS_CONFIG"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ursdevice.h
api_name:
- URS_CONFIG
product:
- Windows
targetos: Windows
req.typenames: URS_CONFIG, *PURS_CONFIG
---

# _URS_CONFIG structure


## -description


Contains pointers to event callback functions implemented by the URS client driver for a USB dual-role controller. Initialize this structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>.


## -struct-fields




### -field Size

The size of this structure.


### -field HostInterfaceType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/urstypes/ne-urstypes-_urs_host_interface_type">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of USB host controller: EHCI, xHCI, or other.


### -field EvtUrsFilterRemoveResourceRequirements

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function.


### -field EvtUrsSetRole

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ursdevice/nc-ursdevice-evt_urs_set_role">EVT_URS_SET_ROLE</a> callback function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ursdevice/nf-ursdevice-urs_config_init">URS_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>
 

 

