---
UID: NS:wificx._WIFI_DEVICE_CAPABILITIES
tech.root: netvista
title: WIFI_DEVICE_CAPABILITIES (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_DEVICE_CAPABILITIES structure describes a WiFiCx device's capabilities.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_DEVICE_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_DEVICE_CAPABILITIES
 - WIFI_DEVICE_CAPABILITIES
f1_keywords:
 - _WIFI_DEVICE_CAPABILITIES
 - wificx/_WIFI_DEVICE_CAPABILITIES
 - WIFI_DEVICE_CAPABILITIES
 - wificx/WIFI_DEVICE_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_DEVICE_CAPABILITIES** structure describes a WiFiCx device's capabilities.

## -struct-fields

### -field Size

The sum (in bytes) of the sizes of all contained elements.

### -field HardwareRadioState

Specifies whether the radio is enabled by hardware. Valid values are 0 (disabled) and 1 (enabled).

### -field SoftwareRadioState

Specifies whether they radio is enabled by software. Valid values are 0 (disabled) and 1 (enabled).

### -field FirmwareVersion

The firmware version.

### -field ActionFramesSupported

Specifies whether sending and receiving action frames is supported. Valid values are 0 (not supported) and 1 (supported).

### -field NumRxStreams

The supported number of RX spatial streams.

### -field NumTxStreams

The supported number of TX spatial streams.

### -field Support_eCSA

Specifies whether eCSA is supported. Valid values are 0 (not supported) and 1 (supported).

### -field MACAddressRandomization

Specifies whether the adapter supports MAC address randomization. Valid values are 0 (not supported) and 1 (supported).

### -field MACAddressRandomizationMask

A bit mask that specifies for each address bit whether it can be randomized (0) or should keep the same value as the permanent address (1). The default is all zeros.

### -field BluetoothCoexistenceSupport

A [**WDI_BLUETOOTH_COEXISTENCE_SUPPORT**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_bluetooth_coexistence_support.md) enum that defines the supported level of Wi-Fi - Bluetooth coexistence.

### -field SupportsNonWdiOidRequests

Specifies non-WDI OID support. Valid values are:
- 0 : Not supported. OIDs that the Microsoft component does not understand are not forwarded to the adapter.
- 1 : Supported. OIDs that the Microsoft component does not understand are forwarded to the adapter.

### -field FastTransitionSupported

Specifies whether the Fast Transition is supported. Valid values are 0 (not supported) and 1 (supported).

### -field MU_MIMOSupported

Specifies whether Mu-MIMO is supported. Valid values are 0 (not supported) and 1 (supported).

### -field BSSTransitionSupported

Specifies if 802.11v BSS transition is supported. Valid values are 0 (not supported) and 1 (supported).

### -field SAEAuthenticationSupported

Specifies if the device supports SAE authentication. Valid values are 0 (not supported) and 1 (supported).

### -field MBOSupported

Specifies if the device supports Multiband Operation (MBO). Valid values are 0 (not supported) and 1 (supported).

### -field BeaconReportsImplemented

Specifies if the adapter implements beacon report measurements. Valid values are 0 (the adapter does not implement beacon report measurements) and 1 (the adapter implements its own 11k beacon report).

## -remarks

Client drivers pass **WIFI_DEVICE_CAPABILITIES** as a parameter to [**WifiDeviceSetDeviceCapabilities**](nf-wificx-wifidevicesetdevicecapabilities.md) to report device capabilities to WiFiCx.

## -see-also

[**WifiDeviceSetDeviceCapabilities**](nf-wificx-wifidevicesetdevicecapabilities.md) 