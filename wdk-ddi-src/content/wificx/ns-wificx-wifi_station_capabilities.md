---
UID: NS:wificx._WIFI_STATION_CAPABILITIES
tech.root: netvista
title: WIFI_STATION_CAPABILITIES (wificx.h)
ms.date: 03/06/2024
targetos: Windows
description: The WIFI_STATION_CAPABILITIES structure describes the station capabilities for a WiFiCx device.
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

### -field MaxMLOLinksSupported

The maximum number of links that the hardware supports for Multi-Link Operation (MLO) connections.

### -field MLOAddressesList

A pointer to an array of [**WDI_MAC_ADDRESS**](../dot11wificxintf/ns-dot11wificxintf-wdi_mac_address.md) structures that represent MLO MAC addresses with **MaxMLOLinksSupported** elements. The number of entries in **MLOAddressesList** must match **MaxMLOLinksSupported**. This will indicate that the driver is capable of setting up MLO links.

### -field NumAkmsSupported

The max number of authentication and key management (AKM) suites that the driver supports.

### -field AkmsList

A pointer to an array of [**RSNA_AKM_SUITE**](../windot11/ne-windot11-rsna_akm_suite.md) structures that represent AKM suites, with **NumAkmsSupported** elements. This list should include all the AKM suites that the driver supports and must include the AKM 24 if the OS is expected to support Simultaneous Authentication of Equals (SAE) with a 384-bit Pairwise Master Key (PMK). The number of entries in **MLOAddressesList** must match **NumAkmsSupported**.

### -field NumFIPSCertifiedCipherAlgorithms

Number of cipher algorithms for which the device has received FIPS 140 certification.

### -field FIPSCertifiedCipherAlgorithmsList

A pointer to an array of [**DOT11_CIPHER_ALGORITHM**](..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md) structures for which the device has received FIPS 140 certification, with **NumFIPSCertifiedCipherAlgorithms** elements.

### -field MSCSSupported

A BOOLEAN that indicates whether the driver supports Mirrored Stream Classification Service (MSCS).

### -field DSCPToUPMappingSupported

A BOOLEAN that indicates whether the driver supports QoS Mapping (Differentiated Services Code Point (DSCP) to User Priority (UP) Mapping).

### -field MaxNumConfigurableActionFrameWakePatterns

The maximum number of action frame wake patterns that the device supports. Drivers must set **MaxNumConfigurableActionFrameWakePatterns** to at least:
* **1** to support MSCS.
* **2** to support DSCP-to-UP mapping.

If **MaxNumConfigurableActionFrameWakePatterns** is less than the minimum value required for each feature, the OS will disable the feature. 

## -remarks

Call [**WIFI_STATION_CAPABILITIES_INIT**](nf-wificx-wifi_station_capabilities_init.md) to initialize this structure and fill in its **Size** field. Then call [**WifiDeviceSetStationCapabilities**](nf-wificx-wifidevicesetstationcapabilities.md) to report station capabilities to WiFiCx.

## -see-also

[**WIFI_STATION_CAPABILITIES_INIT**](nf-wificx-wifi_station_capabilities_init.md)

[**WifiDeviceSetStationCapabilities**](nf-wificx-wifidevicesetstationcapabilities.md)