---
UID: NF:hidspicx.HIDSPICX_DEVICE_CONFIG_INIT
tech.root: hid
title: HIDSPICX_DEVICE_CONFIG_INIT
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidspicx.h
api_name:
 - HIDSPICX_DEVICE_CONFIG_INIT
f1_keywords:
 - HIDSPICX_DEVICE_CONFIG_INIT
 - hidspicx/HIDSPICX_DEVICE_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **HIDSPICX_DEVICE_CONFIG_INIT** routine is used to initialize a [HIDSPICX_DEVICE_CONFIG](ns-hidspicx-hidspicx_device_config.md) structure before passing it to the to the **HidSpiCxDeviceConfigure** function.

## -parameters

### -param DeviceConfig

A pointer to the client driver-allocated [HIDSPICX_DEVICE_CONFIG](ns-hidspicx-hidspicx_device_config.md) structure.

### -param EvtResetDevice

A pointer to the client driver's implementation of the [EVT_HIDSPICX_RESETDEVICE](nc-hidspicx-evt_hidspicx_resetdevice.md) callback function.

### -param EvtNotifyPowerDown

A pointer to the client driver's implementation of the [EVT_HIDSPICX_NOTIFY_POWERDOWN](nc-hidspicx-evt_hidspicx_notify_powerdown.md) callback function.

### -param InputReportQueue

A **WDFQUEUE** handle to a client-created, non-power-managed, queue for receipt of input report requests from the HID SPI class extension.

### -param OutputReportQueue

A **WDFQUEUE** handle to a client-created, non-power-managed, queue for receipt of output report requests from the HID SPI class extension.

## -remarks

Before passing a [HIDSPICX_DEVICE_CONFIG](ns-hidspicx-hidspicx_device_config.md) structure pointer to the [HidSpiCxDeviceConfigure](nf-hidspicx-hidspicxdeviceconfigure.md) function, it must first be initialized by a call to this macro.

## -see-also

[HidSpiCxDeviceConfigure](nf-hidspicx-hidspicxdeviceconfigure.md)

[HIDSPICX_DEVICE_CONFIG](ns-hidspicx-hidspicx_device_config.md)

[EVT_HIDSPICX_RESETDEVICE](nc-hidspicx-evt_hidspicx_resetdevice.md)

[EVT_HIDSPICX_NOTIFY_POWERDOWN](nc-hidspicx-evt_hidspicx_notify_powerdown.md)
