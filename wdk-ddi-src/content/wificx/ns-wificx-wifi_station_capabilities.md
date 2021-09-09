---
UID: NS:wificx._WIFI_STATION_CAPABILITIES
tech.root: netvista
<<<<<<< HEAD
title: WIFI_STATION_CAPABILITIES (wificx.h)
ms.date: 08/26/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_STATION_CAPABILITIES structure describes the station capabilities for a WiFiCx device.
=======
title: WIFI_STATION_CAPABILITIES
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_STATION_CAPABILITIES structure for internal use only. Don't use this structure in your code."
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
req.typenames: WIFI_STATION_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_STATION_CAPABILITIES
 - WIFI_STATION_CAPABILITIES
f1_keywords:
 - _WIFI_STATION_CAPABILITIES
 - wificx/_WIFI_STATION_CAPABILITIES
 - WIFI_STATION_CAPABILITIES
 - wificx/WIFI_STATION_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **WIFI_STATION_CAPABILITIES** structure describes the station capabilities for a WiFiCx device.

## -struct-fields

### -field Size

The sum (in bytes) of the sizes of all contained elements.

### -field ScanSSIDListSize

The scan SSID list size.

### -field DesiredSSIDListSize

The desired SSID list size.

### -field PrivacyExemptionListSize

The privacy exemption list size.

### -field KeyMappingTableSize

The key mapping table size.

### -field DefaultKeyTableSize

The default key table size.

### -field WEPKeyValueMaxLength

The maximum length of the WEP key value.

### -field MaxNumPerSTA

The maximum number of per STA default key tables.

### -field SupportedQOSFlags

Specifies whether WMM QOS is supported. Valid values are 0 (not supported) and 1 (supported).

### -field HostFIPSModeImplemented

Specifies whether host FIPS mode is supported. Valid values are 0 (not supported) and 1 (supported).

### -field MFPCapable

Specifies whether management frame protection (MFP) is supported. Valid values are 0 (not supported) and 1 (supported).

### -field AutoPowerSaveMode

Specifies whether auto power save is supported. Valid values are 0 (not supported) and 1 (supported).

### -field BSSListCachemanagement

Specifies if the adapter would maintain the station BSS list cache. Valid values are 0 (no) and 1 (yes).

### -field ConnectBSSSelectionOverride

Specifies if on a Station connect the adapter may attempt association to a BSSID that is not specified in the Preferred BSSID list. Valid values are 0 (no) and 1 (yes).

### -field MaxNetworkOffloadListSize

Specifies the supported number of network offload entries.

### -field HESSIDConnectionSupported

Specifies whether the ability to connect to HESSIDs is supported. Valid values are 0 (not supported) and 1 (supported).

### -field FTMAsInitiatorSupport

Specifies whether the FTM procedures as initiator are supported. Valid values are 0 (not supported) and 1 (supported).

### -field FTMNumberOfSupportedTargets

Number of target STAs supported per FTM request task.

### -field HostWPA3FIPSModeEnabled

Specifies whether host-FIPS mode for WPA3 is enabled. Valid values are 0 (disabled) and 1 (enabled).

### -field NumSupportedUnicastAlgorithms

The number of unicast algorithms supported.

### -field UnicastAlgorithmsList

A pointer to an array of unicast cipher algorithms formatted as [**DOT11_AUTH_CIPHER_PAIR**](../wlantypes/ns-wlantypes-dot11_auth_cipher_pair.md) structures. The length of this array is specified by the **NumSupportedUnicastAlgorithms** member.

### -field NumSupportedMulticastDataAlgorithms

The number of multicast data cipher algorithms supported.

### -field MulticastDataAlgorithmsList

A pointer to an array of multicast data cipher algorithms formatted as [**DOT11_AUTH_CIPHER_PAIR**](../wlantypes/ns-wlantypes-dot11_auth_cipher_pair.md) structures. The length of this array is specified by the **NumSupportedMulticastDataAlgorithms** member.

### -field NumSupportedMulticastMgmtAlgorithms

The number of multicast management algorithms supported.

### -field MulticastMgmtAlgorithmsList

A pointer to an array of multicast management algorithms formatted as [**DOT11_AUTH_CIPHER_PAIR**](../wlantypes/ns-wlantypes-dot11_auth_cipher_pair.md) structures. The length of this array is specified by the **NumSupportedMulticastMgmtAlgorithms** member.

### -field NumSecondaryStaBandCombinations

The number of secondary STA band combinations. If this value is **0**, then the Secondary STA capability will not be set.

### -field SecondaryStaBandsCombinations

A pointer to an array of [**WIFI_STA_BANDS_COMBINATION**](ns-wificx-wifi_sta_bands_combination.md) structures. If this value is **NULL**, then the Secondary STA capability will not be set.

## -remarks

Client drivers pass **WIFI_STATION_CAPABILITIES** as a parameter to [**WifiDeviceSetStationCapabilities**](nf-wificx-wifidevicesetstationcapabilities.md) to report station capabilities to WiFiCx.

## -see-also

[**WifiDeviceSetStationCapabilities**](nf-wificx-wifidevicesetstationcapabilities.md)