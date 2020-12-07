---
UID: NE:wdfdevice._WDF_DEVICE_POWER_STATE
title: _WDF_DEVICE_POWER_STATE (wdfdevice.h)
description: The WDF_DEVICE_POWER_STATE enumeration identifies all of the states that the framework's power state machine can enter.
old-location: wdf\wdf_device_power_state.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_POWER_STATE enumeration"]
ms.keywords: "*PWDF_DEVICE_POWER_STATE, PWDF_DEVICE_POWER_STATE, PWDF_DEVICE_POWER_STATE enumeration pointer, WDF_DEVICE_POWER_STATE, WDF_DEVICE_POWER_STATE enumeration"
req.header: wdfdevice.h
req.include-header: Wdf.h
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
req.typenames: WDF_DEVICE_POWER_STATE, *PWDF_DEVICE_POWER_STATE
f1_keywords:
 - _WDF_DEVICE_POWER_STATE
 - wdfdevice/_WDF_DEVICE_POWER_STATE
 - PWDF_DEVICE_POWER_STATE
 - wdfdevice/PWDF_DEVICE_POWER_STATE
 - WDF_DEVICE_POWER_STATE
 - wdfdevice/WDF_DEVICE_POWER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_DEVICE_POWER_STATE
---

# _WDF_DEVICE_POWER_STATE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This enumeration is for Microsoft internal use only.

The <b>WDF_DEVICE_POWER_STATE</b> enumeration identifies all of the states that the framework's power state machine can enter.

## -remarks

The <b>WDF_DEVICE_POWER_STATE</b> enumeration is used as a member type in the <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_power_notification_data">WDF_DEVICE_POWER_NOTIFICATION_DATA</a> structure and as the return type for the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a> method.
