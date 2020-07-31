---
UID: NS:windot11._DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
title: _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_ofdm_frequency_list.htm
tech.root: netvista
ms.assetid: 0c967358-821b-4f78-acbc-dacee24dcd57
ms.date: 02/16/2018
keywords: ["_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure"]
ms.keywords: "*PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_428915da-fa98-469c-829b-5d0313a59c3b.xml, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, netvista.dot11_supported_ofdm_frequency_list, windot11/DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
f1_keywords:
 - "windot11/DOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
 - "DOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
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
- DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
targetos: Windows
req.typenames: DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST
product:
- Windows 10 or later.
---

# _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure specifies a list of channel center frequencies that
  the 802.11 station can operate with.


## -syntax


```cpp
typedef struct _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST {
  ULONG                          uNumOfEntries;
  ULONG                          uTotalNumOfEntries;
  DOT11_SUPPORTED_OFDM_FREQUENCY dot11SupportedOFDMFrequency[1];
} DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST;
```


## -struct-fields




### -field uNumOfEntries

The number of entries in the
     <b>dot11SupportedOFDMFrequency</b> array.


### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>dot11SupportedOFDMFrequency</b> array can contain.


### -field dot11SupportedOFDMFrequency

An array that specifies the list of supported channel center frequencies that the NIC can operate
     with. Each element in this list is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
     DOT11_SUPPORTED_OFDM_FREQUENCY</a> structure.


## -remarks



A miniport driver returns the DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure when queried by
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
    OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
   OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>



<a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
   DOT11_SUPPORTED_OFDM_FREQUENCY</a>



 

 


