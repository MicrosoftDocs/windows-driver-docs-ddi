---
UID: NC:ufxclient.EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
title: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY (ufxclient.h)
description: The client driver's implementation to set charger information that it uses to enable charging over USB.
old-location: buses\evt_ufx_device_proprietary_charger_set_property.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback function"]
ms.keywords: EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY, EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback, EvtUfxDeviceProprietaryChargerSetProperty, EvtUfxDeviceProprietaryChargerSetProperty callback function [Buses], PFN_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY, PFN_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback function pointer [Buses], buses.evt_ufx_device_proprietary_charger_set_property, ufxclient/EvtUfxDeviceProprietaryChargerSetProperty
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
 - ufxclient/EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ufxclient.h
api_name:
 - EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY
---

# EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback function


## -description

The client driver's implementation to set charger information that it uses to enable charging over USB.

## -parameters

### -param unnamedParam1 [in]

The handle to a  USB device object that the client driver received in a previous call to  the <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


### -param unnamedParam2 [in]

The handle framework request object that for an <a href="/windows-hardware/drivers/ddi/charging/ni-charging-ioctl_internal_configure_charger_property">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a> request from the battery minidriver.

## -remarks

<i>EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</i> is an optional event callback.

<i>WdfRequest</i> is contains a request for <a href="/windows-hardware/drivers/ddi/charging/ni-charging-ioctl_internal_configure_charger_property">IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</a>, which specifies a charger ID that is known by the client driver and battery miniclass driver, and a voltage value in millivolts.  The client driver can use this information to enable charging over the USB port at an appropriate current/voltage level.

## -see-also

<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete">UfxDeviceProprietaryChargerDetectComplete</a>

