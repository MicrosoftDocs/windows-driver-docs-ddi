---
UID: NS:wificx._WIFI_WIFIDIRECT_CAPABILITIES
tech.root: netvista
<<<<<<< HEAD
title: WIFI_WIFIDIRECT_CAPABILITIES (wificx.h)
ms.date: 08/25/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_WIFIDIRECT_CAPABILITIES structure describes the Wi-Fi Direct capabilities for a WiFiCx device.
=======
title: WIFI_WIFIDIRECT_CAPABILITIES
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_WIFIDIRECT_CAPABILITIES structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_WIFIDIRECT_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_WIFIDIRECT_CAPABILITIES
 - WIFI_WIFIDIRECT_CAPABILITIES
f1_keywords:
 - _WIFI_WIFIDIRECT_CAPABILITIES
 - wificx/_WIFI_WIFIDIRECT_CAPABILITIES
 - WIFI_WIFIDIRECT_CAPABILITIES
 - wificx/WIFI_WIFIDIRECT_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_WIFIDIRECT_CAPABILITIES** structure describes the Wi-Fi Direct capabilities for a WiFiCx device.

## -struct-fields

### -field Size

The sum (in bytes) of the sizes of all contained elements.

### -field WFDRoleCount

Number of supported Wi-Fi Direct Role Ports

### -field ConcurrentGOCount

Specifies the concurrent Group Owner count.

### -field ConcurrentClientCount

Specifies the concurrent Client count.

### -field ServiceDiscoverySupported

Specifies whether Service discovery is supported.
Valid values are 0 (not supported) and 1 (supported).

### -field ServiceNameDiscoverySupported

Wi-Fi Direct Service Names Discovery support. Specifies whether, when given a list of service name hashes, the adapter can probe for service hashes and indicate the responses as they arrive.
Valid values are 0 (not supported) and 1 (supported).

### -field ServiceInformationDiscoverySupported

Wi-Fi Direct Service Information Discovery support. Specifies whether, when given a list of service name hashes, the adapter can perform probes and ANQP queries to get full service information.
Valid values are 0 (not supported) and 1 (supported).

### -field ServiceNameAdvertisementsMaxBytesSupported

Specifies the maximum supported number of Service Name Advertisements bytes (to be sent in the beacon and probe responses). This sets a hard limit on the number of services that can be advertised.

### -field ServiceInformationAdvertisementsMaxBytesSupported

Specifies the maximum supported number of Service Information Advertisement bytes the adapter can respond to using the GAS protocol. This is only valid if the device supports responding to Service Advertisement queries. This value is for firmware optimization so that the firmware does not wake up the host to respond to every query. The operating system does not limit the number of service advertisements if the firmware has a limitation because there is a fallback in the operating system. If the firmware cannot handle the ANQP query response, it should pass up the request and the operating system handles it.

### -field BackgroundDiscoverySupported

Background discovery of Wi-Fi Direct devices and services. Specifies whether the adapter can periodically query for Wi-Fi Direct devices and service names so any new devices show up within 5 minutes of becoming visible.
Valid values are 0 (not supported) and 1 (supported).

### -field ClientDiscoverabilitySupported

Specifies whether Client Discoverability is supported.
Valid values are 0 (not supported) and 1 (supported).

### -field InfrastructureManagementSupported

Specifies whether infrastructure management is supported.
Valid values are 0 (not supported) and 1 (supported).

### -field DeviceAddress

The device address in network byte order.

### -field DiscoveryFilterListSize

The discovery filter list size.

### -field GOClientTableSize

The GO client table size.

### -field MaxVendorSpecificExtensionIESize

The maximum size, in bytes, of vendor specific extension IEs that can be added to WFD management frames.

### -field PassiveAvailabilityListenStateSupported

Specifies whether the ability to listen for P2P Services in the background is supported. Valid values are 0 (not supported) and 1 (supported).

### -field OperatingChannelUpdatesSupported

Specifies whether the adapter supports indicating updates to the GO operating channel(s).
Valid values are 0 (not supported) and 1 (supported).

### -field GOon5GHzBandSupported

Specifies whether the adapter supports operating a GO on the 5GHz band.
Valid values are 0 (not supported) and 1 (supported).

### -field ScanSSIDListSize

The scan SSID list size.

### -field DesiredSSIDListSize

The desired SSID list size.

### -field PrivacyExemptionListSize

The privacy exemption list size.

### -field AssociationTableSize

The association table size.

### -field DefaultKeyTableSize

The default key table size.

### -field WEPKeyValueMaxLength

The maximum length of the WEP key value.

### -field NumSupportedUnicastAlgorithms

The number of unicast algorithms supported.

### -field UnicastAlgorithms

A pointer to an array of unicast cipher algorithms formatted as [**DOT11_AUTH_CIPHER_PAIR**](../wlantypes/ns-wlantypes-dot11_auth_cipher_pair.md) structures. The length of this array is specified by the **NumSupportedUnicastAlgorithms** member.

### -field NumSupportedMulticastDataAlgorithms

The number of multicast data cipher algorithms supported.

### -field MulticastDataAlgorithms

A pointer to an array of multicast data cipher algorithms formatted as [**DOT11_AUTH_CIPHER_PAIR**](../wlantypes/ns-wlantypes-dot11_auth_cipher_pair.md) structures. The length of this array is specified by the **NumSupportedMulticastDataAlgorithms** member.

### -field NumInterfaceAddresses

The number of interface addresses supported.

### -field InterfaceAddressList

A pointer to an array of interface addresses formatted as [**WDI_MAC_ADDRESS**](../dot11wificxintf/ns-dot11wificxintf-wdi_mac_address.md) structures. The length of this array is specified by the **NumInterfaceAddresses** member.

## -remarks

Client drivers pass **WIFI_WIFIDIRECT_CAPABILITIES** as a parameter to [**WifiDeviceSetWiFiDirectCapabilities**](nf-wificx-wifidevicesetwifidirectcapabilities.md) to report Wi-Fi Direct capabilities to WiFiCx.

## -see-also

[**WifiDeviceSetWiFiDirectCapabilities**](nf-wificx-wifidevicesetwifidirectcapabilities.md)