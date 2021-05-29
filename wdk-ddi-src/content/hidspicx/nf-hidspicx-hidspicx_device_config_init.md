---
UID: NF:hidspicx.HIDSPICX_DEVICE_CONFIG_INIT
tech.root: hid
title: HIDSPICX_DEVICE_CONFIG_INIT
ms.date: 
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
 - 
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

The **HIDSPICX_DEVICE_CONFIG_INIT** routine is used to initialize a HIDSPICX_DEVICE_CONFIG structure before passing it to the to the **HidSpiCxDeviceConfigure** function.

## -parameters

### -param DeviceConfig

Output parameter, pointing to a caller-provided HIDSPICX_DEVICE_CONFIG structure. This may be a stack allocated structure.

### -param EvtResetDevice

### -param EvtNotifyPowerDown

### -param InputReportQueue

### -param OutputReportQueue

## -remarks

Before passing a PHIDSPICX_DEVICE_CONFIG structure pointer to the HidSpiCxDeviceConfigure function, it must first be initialized by a call to this macro.

## -see-also
