---
UID: NS:ntifs._SecPkgCredentials_KdcNetworkSettingsW
tech.root: ifsk
title: SecPkgCredentials_KdcNetworkSettingsW
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SecPkgCredentials_KdcNetworkSettingsW structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SecPkgCredentials_KdcNetworkSettingsW, *PSecPkgCredentials_KdcNetworkSettingsW
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SecPkgCredentials_KdcNetworkSettingsW
 - PSecPkgCredentials_KdcNetworkSettingsW
 - SecPkgCredentials_KdcNetworkSettingsW
f1_keywords:
 - _SecPkgCredentials_KdcNetworkSettingsW
 - ntifs/_SecPkgCredentials_KdcNetworkSettingsW
 - PSecPkgCredentials_KdcNetworkSettingsW
 - ntifs/PSecPkgCredentials_KdcNetworkSettingsW
 - SecPkgCredentials_KdcNetworkSettingsW
 - ntifs/SecPkgCredentials_KdcNetworkSettingsW
dev_langs:
 - c++
helpviewer_keywords:
 - _SecPkgCredentials_KdcNetworkSettingsW
---

## -description

The **SecPkgCredentials_KdcNetworkSettingsW** structure is used to configure network settings for Kerberos Key Distribution Center (KDC) communications in secure environments. It is typically used in scenarios where specific network configurations are required for secure communication with KDCs.

## -struct-fields

### -field Version

Specifies the version of the network settings structure. For this structure, it should be set to **KDC_NETWORK_SETTINGS_V2**.

### -field Flags

Specifies flags that dictate the behavior of the network settings. Valid flags include:

| Flag | Description |
| ---- | ----------- |
| KDC_NETWORK_SETTINGS_FLAGS_FORCEPROXY (0x1) | Forces the use of a proxy for KDC communications. |
| KDC_NETWORK_SETTINGS_FLAGS_CONFIGURE_PROXY (0x80000000) | Indicates that proxy configuration is required. |
| KDC_NETWORK_SETTINGS_FLAGS_CONFIGURE_DISCOVERY (0x40000000) | Indicates that domain controller discovery configuration is required. |

### -field ProxyServerOffset

Offset, in bytes, from the beginning of the structure to the proxy server string. This field is optional.

### -field ProxyServerLength

Length, in bytes, of the proxy server string.

### -field ClientTlsCredOffset

Offset, in bytes, from the beginning of the structure to the client TLS credentials. This field is optional.

### -field ClientTlsCredLength

Length, in bytes, of the client TLS credentials.

### -field DcDiscoveryFlags

Flags related to domain controller discovery. Valid flags include:

| Flag | Description |
| ---- | ----------- |
| KDC_NETWORK_DISCOVERY_FLAGS_DS13_REQUIRED (0x80000000) | Indicates that DS 1.3 discovery is required. |
