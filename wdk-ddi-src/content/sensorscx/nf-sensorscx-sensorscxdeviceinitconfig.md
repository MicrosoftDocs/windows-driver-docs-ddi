---
UID: NF:sensorscx.SensorsCxDeviceInitConfig
title: SensorsCxDeviceInitConfig function (sensorscx.h)
description: This function configures the sensor device.
old-location: sensors\sensorscxdeviceinitconfig.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["SensorsCxDeviceInitConfig function"]
ms.keywords: SensorsCxDeviceInitConfig, SensorsCxDeviceInitConfig function [Sensor Devices], sensors.sensorscxdeviceinitconfig, sensorscx/SensorsCxDeviceInitConfig
req.header: sensorscx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SensorsCxDeviceInitConfig
 - sensorscx/SensorsCxDeviceInitConfig
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - SensorsCx.h
api_name:
 - SensorsCxDeviceInitConfig
---

# SensorsCxDeviceInitConfig function


## -description

This function configures the sensor device.

## -parameters

### -param pFxDeviceInit [in, out]


A reference to WDFDEVICE_INIT.

### -param pFdoAttributes [in, out]


A reference to WDF_OBJECT_ATTRIBUTES.

### -param Flags [in]


The flags for the sensor driver. Reserved set to 0.

## -returns

This function returns STATUS_SUCCESS when completed successfully. When an invalid parameter is supplied or this function fails, STATUS_INVALID_PARAMETER is returned. This function can also return other NTSTATUS values.

