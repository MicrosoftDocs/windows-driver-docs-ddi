---
UID: NE:pointofservicedriverinterface._PosDeviceControlType
title: PosDeviceControlType (pointofservicedriverinterface.h)
description: This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.
tech.root: pos
ms.date: 04/19/2022
keywords: ["PosDeviceControlType enumeration"]
ms.keywords: BarcodeScannerInjectEvent, CheckHealth, ClaimDevice, GetDeviceBasics, GetProperty, Invalid, MsrAuthenticateDevice, MsrDeAuthenticateDevice, MsrRetrieveDeviceAuthentication, MsrUpdateKey, PosDeviceControlType, PosDeviceControlType enumeration, ReleaseDevice, ResetStatistics, RetainDevice, RetrieveStatistics, SetProperty, UpdateStatistics, _MaxDeviceControlType, _PosDeviceControlType, pointofservicedriverinterface/BarcodeScannerInjectEvent, pointofservicedriverinterface/CheckHealth, pointofservicedriverinterface/ClaimDevice, pointofservicedriverinterface/GetDeviceBasics, pointofservicedriverinterface/GetProperty, pointofservicedriverinterface/Invalid, pointofservicedriverinterface/MsrAuthenticateDevice, pointofservicedriverinterface/MsrDeAuthenticateDevice, pointofservicedriverinterface/MsrRetrieveDeviceAuthentication, pointofservicedriverinterface/MsrUpdateKey, pointofservicedriverinterface/PosDeviceControlType, pointofservicedriverinterface/ReleaseDevice, pointofservicedriverinterface/ResetStatistics, pointofservicedriverinterface/RetainDevice, pointofservicedriverinterface/RetrieveStatistics, pointofservicedriverinterface/SetProperty, pointofservicedriverinterface/UpdateStatistics, pointofservicedriverinterface/_MaxDeviceControlType, pos.posdevicecontroltype
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
req.target-type: Windows
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
req.typenames: PosDeviceControlType
f1_keywords:
 - _PosDeviceControlType
 - pointofservicedriverinterface/_PosDeviceControlType
 - PosDeviceControlType
 - pointofservicedriverinterface/PosDeviceControlType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - _PosDeviceControlType
 - PosDeviceControlType
---

## -description

This enumeration defines values for the IOCTLs of the scanner driver and magnetic stripe reader (MSR) driver.

## -enum-fields

### -field _MinDeviceControlType

Reserved for internal use.

### -field Invalid

The event code is not valid.

### -field GetProperty

Represents [IOCTL_POINT_OF_SERVICE_GET_PROPERTY](./ni-pointofservicedriverinterface-ioctl_point_of_service_get_property.md).

### -field SetProperty

Represents [IOCTL_POINT_OF_SERVICE_SET_PROPERTY](./ni-pointofservicedriverinterface-ioctl_point_of_service_set_property.md).

### -field ClaimDevice

Represents [IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md).

### -field ReleaseDevice

Represents [IOCTL_POINT_OF_SERVICE_RELEASE_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_release_device.md).

### -field RetainDevice

Represents [IOCTL_POINT_OF_SERVICE_RETAIN_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_retain_device.md).

### -field RetrieveStatistics

Represents [IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS](./ni-pointofservicedriverinterface-ioctl_point_of_service_retrieve_statistics.md).

### -field ResetStatistics

Represents [IOCTL_POINT_OF_SERVICE_RESET_STATISTICS](./ni-pointofservicedriverinterface-ioctl_point_of_service_reset_statistics.md).

### -field UpdateStatistics

Represents [IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS](./ni-pointofservicedriverinterface-ioctl_point_of_service_update_statistics.md).

### -field CheckHealth

Represents [IOCTL_POINT_OF_SERVICE_CHECK_HEALTH](./ni-pointofservicedriverinterface-ioctl_point_of_service_check_health.md).

### -field GetDeviceBasics

Represents [IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS](./ni-pointofservicedriverinterface-ioctl_point_of_service_get_device_basics.md).

### -field BarcodeScannerInjectEvent

Defines the **BarcodeScannerInjectEvent** constant.

### -field MsrRetrieveDeviceAuthentication

Represents [IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION](./ni-pointofservicedriverinterface-ioctl_point_of_service_msr_retrieve_device_authentication.md).

### -field MsrAuthenticateDevice

Represents [IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_msr_authenticate_device.md).

### -field MsrDeAuthenticateDevice

Represents [IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE](./ni-pointofservicedriverinterface-ioctl_point_of_service_msr_deauthenticate_device.md).

### -field MsrUpdateKey

Represents [IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY](./ni-pointofservicedriverinterface-ioctl_point_of_service_msr_update_key.md).

### -field StartBarcodeScannerSoftwareTrigger

Defines the **StartBarcodeScannerSoftwareTrigger** constant.

### -field StopBarcodeScannerSoftwareTrigger

Defines the **StopBarcodeScannerSoftwareTrigger** constant.

### -field BarcodeScannerGetSymbologyAttributes

Defines the **BarcodeScannerGetSymbologyAttributes** constant.

### -field BarcodeScannerSetSymbologyAttributes

Defines the **BarcodeScannerSetSymbologyAttributes** constant.

### -field _MaxDeviceControlType

Reserved for internal use.

## -remarks

This enumeration provides values for each IOCTL that you can send to the device driver. It is a convenient way to indicate which IOCTL to dispatch when calling functions like **SendDeviceCommand()**.