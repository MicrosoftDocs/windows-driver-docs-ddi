---
UID: NC:wlanihv.DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM
title: DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetmulticastcipheralgorithm.htm
tech.root: netvista
ms.assetid: af023bc5-af3e-429c-b9c4-c06e5598cfaf
ms.date: 02/16/2018
keywords: ["DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM callback"]
ms.keywords: DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM, Dot11ExtSetMulticastCipherAlgorithm, Dot11ExtSetMulticastCipherAlgorithm callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_67af4c54-7246-4d6e-a82f-35a7b23c8200.xml, netvista.dot11extsetmulticastcipheralgorithm, wlanihv/Dot11ExtSetMulticastCipherAlgorithm
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
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
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
f1_keywords:
 - DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM
 - wlanihv/DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wlanihv.h
api_name:
 - Dot11ExtSetMulticastCipherAlgorithm
---

# DOT11EXT_SET_MULTICAST_CIPHER_ALGORITHM callback


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The IHV Extensions DLL calls the
  <b>Dot11ExtSetMulticastCipherAlgorithm</b> function to enable a multicast cipher
  algorithm on the wireless LAN (WLAN) adapter.

## -parameters

### -param hDot11SvcHandle 

[in, optional]
The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

### -param dwMulticastCipherAlgo 

[in]
A
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> enumerator
     value that identifies the multicast cipher algorithm.


If the value is within the range of <b>DOT11_CIPHER_ALGO_IHV_START</b> through DOT11_CIPHER_ALGO_IHV_END,
     the IHV Extensions DLL enables a proprietary cipher algorithm supported by the WLAN adapter.

Otherwise, the DLL is responsible for processing a standard cipher algorithm supported by the
     operating system. In this situation, the operating system is not involved with any aspect of the cipher
     algorithm, including key management and replay protection, over a basic service set (BSS) network
     connection through the WLAN adapter.

<div class="alert"><b>Note</b>  The value of
     <i>dwMulticastCipherAlgo</i> must match the value of a cipher algorithm returned by the Native 802.11
     miniport driver through setting the appropriate <i>xxx</i><b>AlgoPairs</b> members of the  <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure, which must match the values that would be returned by queries of
     <a href="/previous-versions/windows/embedded/gg157261(v=winembedded.80)">OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or
     <a href="/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.</div>

## -returns

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.

## -prototype

```cpp
DWORD WINAPI * Dot11ExtSetMulticastCipherAlgorithm(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwMulticastCipherAlgo
);
```

## -see-also

<a href="/previous-versions/windows/embedded/gg157261(v=winembedded.80)">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>



<a href="/windows-hardware/drivers/network/oid-dot11-supported-multicast-algorithm-pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>