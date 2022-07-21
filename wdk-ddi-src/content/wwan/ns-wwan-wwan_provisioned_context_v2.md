---
UID: NS:wwan._WWAN_PROVISIONED_CONTEXT_V2
tech.root: netvista
title: WWAN_PROVISIONED_CONTEXT_V2
ms.date: 01/18/2022
targetos: Windows
description: The WWAN_PROVISIONED_CONTEXT_V2 structure represents a provisioned context that is supported by a mobile broadband (MBB) device.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_PROVISIONED_CONTEXT_V2, *PWWAN_PROVISIONED_CONTEXT_V2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_PROVISIONED_CONTEXT_V2
 - PWWAN_PROVISIONED_CONTEXT_V2
 - WWAN_PROVISIONED_CONTEXT_V2
f1_keywords:
 - _WWAN_PROVISIONED_CONTEXT_V2
 - wwan/_WWAN_PROVISIONED_CONTEXT_V2
 - PWWAN_PROVISIONED_CONTEXT_V2
 - wwan/PWWAN_PROVISIONED_CONTEXT_V2
 - WWAN_PROVISIONED_CONTEXT_V2
 - wwan/WWAN_PROVISIONED_CONTEXT_V2
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_PROVISIONED_CONTEXT_V2
---

## -description

The **WWAN_PROVISIONED_CONTEXT_V2** structure represents a provisioned context that is supported by a mobile broadband (MBB) device. **WWAN_PROVISIONED_CONTEXT_V2** is only used in MBB driver versions 2.170 and above.

## -struct-fields

### -field basicInfo

A [**WWAN_CONTEXT**](ns-wwan-_wwan_context.md) structure that represents the basic information for this provisioned context.

### -field IPType

A [**WWAN_IP_TYPE**](ne-wwan-_wwan_ip_type.md) value that specifies the supported IP types for this provisioned context.

### -field Enable

A [**WWAN_CONTEXT_ENABLE**](ne-wwan-_wwan_context_enable.md) value that specifies whether the context is enabled or disabled in the modem.

### -field Roaming

A [**WWAN_CONTEXT_ROAMING_CONTROL**](ne-wwan-_wwan_context_roaming_control.md) value that specifies which roaming condition applies to this context.

### -field MediaType

A [**WWAN_CONTEXT_MEDIA_TYPE**](ne-wwan-_wwan_context_media_type.md) value that specifies the supported media types for this provisioned context.

### -field Source

A [**WWAN_CONFIGURATION_SOURCE**](ne-wwan-_wwan_configuration_source.md) value that specifies the creation source of the context.

### -field Reserved

Reserved for system use. Miniport drivers should not read or write to this value.

### -field Snssai

A [**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md) structure representing a single Network Slice Selection Assistance Information (NSSAI).

## -remarks

**WWAN_PROVISIONED_CONTEXT_V2** is used as a response to [OID_WWAN_PROVISIONED_CONTEXT](/windows-hardware/drivers/network/oid-wwan-provisioned-contexts) set requests.

## -see-also

[**WWAN_CONTEXT**](ns-wwan-_wwan_context.md)

[**WWAN_IP_TYPE**](ne-wwan-_wwan_ip_type.md)

[**WWAN_CONTEXT_ENABLE**](ne-wwan-_wwan_context_enable.md)

[**WWAN_CONTEXT_ROAMING_CONTROL**](ne-wwan-_wwan_context_roaming_control.md)

[**WWAN_CONTEXT_MEDIA_TYPE**](ne-wwan-_wwan_context_media_type.md)

[**WWAN_CONFIGURATION_SOURCE**](ne-wwan-_wwan_configuration_source.md)

[**WWAN_SINGLE_NSSAI**](ns-wwan-wwan_single_nssai.md) 

[**WWAN_SET_PROVISIONED_CONTEXT_V2**](../wwan/ns-wwan-wwan_set_provisioned_context_v2.md)


