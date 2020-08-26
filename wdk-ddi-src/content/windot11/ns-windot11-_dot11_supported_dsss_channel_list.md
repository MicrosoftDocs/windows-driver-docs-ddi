---
UID: NS:windot11._DOT11_SUPPORTED_DSSS_CHANNEL_LIST
title: _DOT11_SUPPORTED_DSSS_CHANNEL_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_dsss_channel_list.htm
tech.root: netvista
ms.assetid: 45941a4d-12e0-4a80-b04e-9e349126f5ff
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_DSSS_CHANNEL_LIST structure"]
ms.keywords: "*PDOT11_SUPPORTED_DSSS_CHANNEL_LIST, DOT11_SUPPORTED_DSSS_CHANNEL_LIST, DOT11_SUPPORTED_DSSS_CHANNEL_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_cf2e493f-66e9-49ae-aed8-3c7b220b836f.xml, PDOT11_SUPPORTED_DSSS_CHANNEL_LIST, PDOT11_SUPPORTED_DSSS_CHANNEL_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_DSSS_CHANNEL_LIST, netvista.dot11_supported_dsss_channel_list, windot11/DOT11_SUPPORTED_DSSS_CHANNEL_LIST, windot11/PDOT11_SUPPORTED_DSSS_CHANNEL_LIST"
f1_keywords:
 - "windot11/DOT11_SUPPORTED_DSSS_CHANNEL_LIST"
 - "DOT11_SUPPORTED_DSSS_CHANNEL_LIST"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_SUPPORTED_DSSS_CHANNEL_LIST
targetos: Windows
req.typenames: DOT11_SUPPORTED_DSSS_CHANNEL_LIST, *PDOT11_SUPPORTED_DSSS_CHANNEL_LIST
product:
- Windows 10 or later.
---

# _DOT11_SUPPORTED_DSSS_CHANNEL_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_DSSS_CHANNEL_LIST structure specifies a list of frequency channels that the
  802.11 station can operate with.


## -syntax


```cpp
typedef struct _DOT11_SUPPORTED_DSSS_CHANNEL_LIST {
  ULONG                        uNumOfEntries;
  ULONG                        uTotalNumOfEntries;
  DOT11_SUPPORTED_DSSS_CHANNEL dot11SupportedDSSSChannel[1];
} DOT11_SUPPORTED_DSSS_CHANNEL_LIST, *PDOT11_SUPPORTED_DSSS_CHANNEL_LIST;
```


## -struct-fields




### -field uNumOfEntries

The number of entries in the
     <b>dot11SupportedDSSSChannel</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>dot11SupportedDSSSChannel</b> array can contain.


### -field dot11SupportedDSSSChannel

An array that specifies the list of supported frequency channels that the NIC can operate with.
     Each element in this list is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_supported_dsss_channel.md">
     DOT11_SUPPORTED_DSSS_CHANNEL</a> structure.


## -remarks



A miniport driver returns the DOT11_SUPPORTED_DSSS_CHANNEL_LIST structure when queried by
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-dsss-channel-list">
    OID_DOT11_SUPPORTED_DSSS_CHANNEL_LIST</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-dsss-channel-list">
   OID_DOT11_SUPPORTED_DSSS_CHANNEL_LIST</a>



<a href="..\windot11\ns-windot11-_dot11_supported_dsss_channel.md">DOT11_SUPPORTED_DSSS_CHANNEL</a>



 

 


