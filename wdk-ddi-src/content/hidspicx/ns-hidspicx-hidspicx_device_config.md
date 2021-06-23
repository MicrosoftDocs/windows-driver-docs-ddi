---
UID: NS:hidspicx._HIDSPICX_DEVICE_CONFIG
tech.root: hid
title: HIDSPICX_DEVICE_CONFIG
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: HIDSPICX_DEVICE_CONFIG, *PHIDSPICX_DEVICE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - hidspicx.h
api_name:
 - _HIDSPICX_DEVICE_CONFIG
 - PHIDSPICX_DEVICE_CONFIG
 - HIDSPICX_DEVICE_CONFIG
f1_keywords:
 - _HIDSPICX_DEVICE_CONFIG
 - hidspicx/_HIDSPICX_DEVICE_CONFIG
 - PHIDSPICX_DEVICE_CONFIG
 - hidspicx/PHIDSPICX_DEVICE_CONFIG
 - HIDSPICX_DEVICE_CONFIG
 - hidspicx/HIDSPICX_DEVICE_CONFIG
dev_langs:
 - c++
---

## -description

The **HIDSPICX_DEVICE_CONFIG** structure provides configuration information to the class extension.

## -struct-fields

### -field Size

This field is set by the [**HIDSPICX_DEVICE_CONFIG_INIT**](nf-hidspicx-hidspicx_device_config_init.md) function.

### -field EvtResetDevice

A pointer to the client driver's implementation of the [**EVT_HIDSPICX_RESETDEVICE**](nc-hidspicx-evt_hidspicx_resetdevice.md) callback function.

### -field EvtNotifyPowerDown

A pointer to the client driver's implementation of the [**EVT_HIDSPICX_NOTIFY_POWERDOWN**](nc-hidspicx-evt_hidspicx_notify_powerdown.md) callback function.

### -field InputReportQueue

A **WDFQUEUE** handle to a client-created, non-power-managed, queue for receipt of input report requests from the HID SPI class extension.

### -field OutputReportQueue

A **WDFQUEUE** handle to a client-created, non-power-managed, queue for receipt of output report requests from the HID SPI class extension.

### -field NumberOfInputReportRequestsToPend

**Optional:** Specifies how many requests are to be placed in the input report queue at a given time. If this is zero, the class extension will choose a default.

### -field Reserved

Must be zero and should not be explicitly set by client drivers.

## -remarks

Instances of this structure must be initialized by calling the [**HIDSPICX_DEVICE_CONFIG_INIT**](nf-hidspicx-hidspicx_device_config_init.md) function.

## -see-also

[**HIDSPICX_DEVICE_CONFIG_INIT**](nf-hidspicx-hidspicx_device_config_init.md)
