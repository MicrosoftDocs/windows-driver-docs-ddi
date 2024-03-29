---
UID: NF:udecxwdfdevice.UDECX_WDF_DEVICE_CONFIG_INIT
title: UDECX_WDF_DEVICE_CONFIG_INIT function (udecxwdfdevice.h)
description: Initializes a UDECX_WDF_DEVICE_CONFIG structure.
old-location: buses\udecx_wdf_device_config_init.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UDECX_WDF_DEVICE_CONFIG_INIT function"]
ms.keywords: UDECX_WDF_DEVICE_CONFIG_INIT, UDECX_WDF_DEVICE_CONFIG_INIT function [Buses], buses.udecx_wdf_device_config_init, udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG_INIT
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UDECX_WDF_DEVICE_CONFIG_INIT
 - udecxwdfdevice/UDECX_WDF_DEVICE_CONFIG_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UDECX_WDF_DEVICE_CONFIG_INIT
---

# UDECX_WDF_DEVICE_CONFIG_INIT function


## -description

Initializes a <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> structure.

## -parameters

### -param Config [out]


A pointer to a <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a> structure to initialize.

### -param EvtUdecxWdfDeviceQueryUsbCapability [in]


A pointer to an <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability">EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY</a> callback function.

## -see-also

<a href="/windows-hardware/drivers/ddi/udecxwdfdevice/ns-udecxwdfdevice-_udecx_wdf_device_config">UDECX_WDF_DEVICE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>
