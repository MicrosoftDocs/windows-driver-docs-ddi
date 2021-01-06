---
UID: NF:ursdevice.URS_CONFIG_INIT
title: URS_CONFIG_INIT function (ursdevice.h)
description: Initializes a URS_CONFIG structure.
old-location: buses\urs_config_init.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["URS_CONFIG_INIT function"]
ms.keywords: URS_CONFIG_INIT, URS_CONFIG_INIT function [Buses], buses.urs_config_init, ursdevice/URS_CONFIG_INIT
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
req.typenames: 
f1_keywords:
 - URS_CONFIG_INIT
 - ursdevice/URS_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ursdevice.h
api_name:
 - URS_CONFIG_INIT
---

# URS_CONFIG_INIT function


## -description

Initializes a <a href="/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a> structure.

## -parameters

### -param Config 

[out]
 A pointer to a <a href="/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a> structure to initialize.

### -param HostInterfaceType 

[in]
 A <a href="/windows-hardware/drivers/ddi/urstypes/ne-urstypes-_urs_host_interface_type">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of host controller that the dual-role controller implements.

### -param EvtUrsFilterRemoveResourceRequirements 

[in]
 A  pointer to a <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function that is implemented by the  client driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/ns-ursdevice-_urs_config">URS_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>
