---
UID: NS:wlanihv._DOT11_MSONEX_RESULT_PARAMS
title: _DOT11_MSONEX_RESULT_PARAMS (wlanihv.h)
description: The DOT11_MSONEX_RESULT_PARAMS structure is used to exchange result parameters with an IHV module.
old-location: netvista\dot11_msonex_result_params.htm
tech.root: netvista
ms.assetid: 21604988-ed1a-419b-b002-ab975e8921ad
ms.date: 02/16/2018
keywords: ["_DOT11_MSONEX_RESULT_PARAMS structure"]
ms.keywords: "*PDOT11_MSONEX_RESULT_PARAMS, DOT11_MSONEX_RESULT_PARAMS, DOT11_MSONEX_RESULT_PARAMS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_52bdb8c1-36cc-43a0-9156-397c3a8549b3.xml, PDOT11_MSONEX_RESULT_PARAMS, PDOT11_MSONEX_RESULT_PARAMS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_MSONEX_RESULT_PARAMS, netvista.dot11_msonex_result_params, wlanihv/DOT11_MSONEX_RESULT_PARAMS, wlanihv/PDOT11_MSONEX_RESULT_PARAMS"
f1_keywords:
 - "wlanihv/DOT11_MSONEX_RESULT_PARAMS"
 - "DOT11_MSONEX_RESULT_PARAMS"
req.header: wlanihv.h
req.include-header: Wlanihv.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wlanihv.h
api_name:
- DOT11_MSONEX_RESULT_PARAMS
targetos: Windows
req.typenames: DOT11_MSONEX_RESULT_PARAMS, *PDOT11_MSONEX_RESULT_PARAMS
req.product: Windows 10 or later.
---

# _DOT11_MSONEX_RESULT_PARAMS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MSONEX_RESULT_PARAMS structure is used to exchange result parameters with an IHV module.


## -syntax


```cpp
typedef struct _DOT11_MSONEX_RESULT_PARAMS {
  ONEX_AUTH_STATUS  Dot11OnexAuthStatus;
  ONEX_REASON_CODE  Dot11OneXReasonCode;
  PBYTE             pbMPPESendKey;
  DWORD             dwMPPESendKeyLen;
  PBYTE             pbMPPERecvKey;
  DWORD             dwMPPERecvKeyLen;
  PDOT11_EAP_RESULT pDot11EapResult;
} DOT11_MSONEX_RESULT_PARAMS, *PDOT11_MSONEX_RESULT_PARAMS;
```


## -struct-fields




### -field Dot11OnexAuthStatus

A
      <a href="https://docs.microsoft.com/windows/desktop/api/dot1x/ne-dot1x-onex_auth_status">ONEX_AUTH_STATUS</a> type that specifies the
      authorization status of the 802.1X exchange.


### -field Dot11OneXReasonCode

A
      <a href="https://docs.microsoft.com/windows/desktop/api/dot1x/ne-dot1x-onex_reason_code">ONEX_REASON_CODE</a> type that specifies the
      reason code of the 802.1X exchange.


### -field pbMPPESendKey

A pointer to a Microsoft Point-to-Point Encryption (MPPE) Send-Key. This key is encrypted and
     should be decrypted by calling the
     <b>CryptUnprotectData</b> function that is documented in the Windows SDK.


### -field dwMPPESendKeyLen

The size, in bytes, of the MPPE Send-Key.


### -field pbMPPERecvKey

A pointer to a Microsoft Point-to-Point Encryption (MPPE) Receive-Key. This key is encrypted and
     should be decrypted by calling the
     <b>CryptUnprotectData</b> function that is documented in the Windows SDK.


### -field dwMPPERecvKeyLen

The size, in bytes, of the MPPE Receive-Key.


### -field pDot11EapResult

A pointer to a
     <a href="..\wlanihv\ns-wlanihv-_dot11_eap_result.md">DOT11_EAP_RESULT</a> structure that contains
     results from an EAP method.


## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/dot1x/ne-dot1x-onex_reason_code">ONEX_REASON_CODE</a>



<a href="..\wlanihv\ns-wlanihv-_dot11_eap_result.md">DOT11_EAP_RESULT</a>



<a href="https://docs.microsoft.com/windows/desktop/api/dot1x/ne-dot1x-onex_auth_status">ONEX_AUTH_STATUS</a>



 

 


