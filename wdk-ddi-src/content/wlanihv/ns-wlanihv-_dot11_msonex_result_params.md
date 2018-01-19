---
UID: NS:wlanihv._DOT11_MSONEX_RESULT_PARAMS
title: _DOT11_MSONEX_RESULT_PARAMS
author: windows-driver-content
description: The DOT11_MSONEX_RESULT_PARAMS structure is used to exchange result parameters with an IHV module.
old-location: netvista\dot11_msonex_result_params.htm
old-project: netvista
ms.assetid: 21604988-ed1a-419b-b002-ab975e8921ad
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_MSONEX_RESULT_PARAMS, DOT11_MSONEX_RESULT_PARAMS, *PDOT11_MSONEX_RESULT_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_MSONEX_RESULT_PARAMS
req.alt-loc: wlanihv.h
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
req.typenames: DOT11_MSONEX_RESULT_PARAMS, *PDOT11_MSONEX_RESULT_PARAMS
req.product: Windows 10 or later.
---

# _DOT11_MSONEX_RESULT_PARAMS structure



## -description

## -syntax

````
typedef struct _DOT11_MSONEX_RESULT_PARAMS {
  ONEX_AUTH_STATUS  Dot11OnexAuthStatus;
  ONEX_REASON_CODE  Dot11OneXReasonCode;
  PBYTE             pbMPPESendKey;
  DWORD             dwMPPESendKeyLen;
  PBYTE             pbMPPERecvKey;
  DWORD             dwMPPERecvKeyLen;
  PDOT11_EAP_RESULT pDot11EapResult;
} DOT11_MSONEX_RESULT_PARAMS, *PDOT11_MSONEX_RESULT_PARAMS;
````


## -struct-fields

### -field Dot11OnexAuthStatus

A 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569845">ONEX_AUTH_STATUS</a> type that specifies the
      authorization status of the 802.1X exchange.


### -field Dot11OneXReasonCode

A 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569846">ONEX_REASON_CODE</a> type that specifies the
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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wlanihv\ns-wlanihv-_dot11_eap_result.md">DOT11_EAP_RESULT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569845">ONEX_AUTH_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569846">ONEX_REASON_CODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MSONEX_RESULT_PARAMS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

