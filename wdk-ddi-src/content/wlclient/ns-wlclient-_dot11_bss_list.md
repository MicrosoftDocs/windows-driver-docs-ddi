---
UID: NS:wlclient._DOT11_BSS_LIST
title: _DOT11_BSS_LIST (wlclient.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_bss_list.htm
tech.root: netvista
ms.assetid: e5c31c4d-8c46-4af1-90de-0311cc90c6c0
ms.date: 02/16/2018
keywords: ["DOT11_BSS_LIST structure"]
ms.keywords: "*PDOT11_BSS_LIST, DOT11_BSS_LIST, DOT11_BSS_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_9b32efe4-bc69-4e6b-9475-449a77c110da.xml, PDOT11_BSS_LIST, PDOT11_BSS_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_BSS_LIST, netvista.dot11_bss_list, wlclient/DOT11_BSS_LIST, wlclient/PDOT11_BSS_LIST"
req.header: wlclient.h
req.include-header: Wlclient.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.typenames: DOT11_BSS_LIST, *PDOT11_BSS_LIST
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11_BSS_LIST
 - wlclient/_DOT11_BSS_LIST
 - PDOT11_BSS_LIST
 - wlclient/PDOT11_BSS_LIST
 - DOT11_BSS_LIST
 - wlclient/DOT11_BSS_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlclient.h
api_name:
 - DOT11_BSS_LIST
---

# _DOT11_BSS_LIST structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_BSS_LIST structure identifies a list of one or more IEEE 802.11 Beacon and Probe Response
  frames.

## -struct-fields

### -field uNumOfBytes

The length, in bytes, of the data within the buffer referenced by the
     <b>pucBuffer</b> member.

### -field pucBuffer

A pointer to a buffer that contains a list of
     <a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a> structures. Each
     DOT11_BSS_ENTRY structure specifies a single 802.11 Beacon and Probe Response frame.


The DOT11_BSS_ENTRY structure has a variable length. However, each entry within the list of
     DOT11_BSS_ENTRY structures does not contain padding for the alignment of the next entry in the
     list.

## -syntax

```cpp
typedef struct _DOT11_BSS_LIST {
  ULONG  uNumOfBytes;
  PUCHAR pucBuffer;
} DOT11_BSS_LIST, *PDOT11_BSS_LIST;
```

## -remarks

The 802.11 Beacon and Probe Response frames within the
    <b>pucBuffer</b> member were received from the underlying 802.11 station during its previous scan
    operation. For more information about this operation, see
    <a href="/windows-hardware/drivers/network/native-802-11-scan-operations">Native 802.11 Scan
    Operations</a>.

## -see-also

<a href="..\windot11\ns-windot11-dot11_bss_entry.md">DOT11_BSS_ENTRY</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_capability_match.md">
   Dot11ExtIhvPerformCapabilityMatch</a>



<a href="/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_create_discovery_profiles.md">
   Dot11ExtIhvCreateDiscoveryProfiles</a>