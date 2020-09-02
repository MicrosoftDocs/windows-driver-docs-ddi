---
UID: NS:wwan._WWAN_AUTH_RESPONSE
title: _WWAN_AUTH_RESPONSE (wwan.h)
description: The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.
old-location: netvista\wwan_auth_response.htm
tech.root: netvista
ms.assetid: CD0B90A1-032D-4F09-827F-E80607AE4EA7
ms.date: 05/02/2018
keywords: ["WWAN_AUTH_RESPONSE structure"]
ms.keywords: "*PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_RESPONSE, WWAN_AUTH_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_RESPONSE, netvista.wwan_auth_response, wwan/PWWAN_AUTH_RESPONSE, wwan/WWAN_AUTH_RESPONSE"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE
f1_keywords:
 - _WWAN_AUTH_RESPONSE
 - wwan/_WWAN_AUTH_RESPONSE
 - PWWAN_AUTH_RESPONSE
 - wwan/PWWAN_AUTH_RESPONSE
 - WWAN_AUTH_RESPONSE
 - wwan/WWAN_AUTH_RESPONSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_AUTH_RESPONSE
---

# _WWAN_AUTH_RESPONSE structure


## -description

The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.

## -struct-fields

### -field AuthMethod

The authentication challenge method used.

### -field u

The container union for the different authentication challenge methods.

### -field u.AuthSim

The esponse from the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.

### -field u.AuthAka

The response from the AKA authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAka, </i>use this member.

### -field u.AuthAkap

The response from the AKA' authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAkap, </i>use this member.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_auth_response">NDIS_WWAN_AUTH_RESPONSE</a> structure uses this structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_auth_response">NDIS_WWAN_AUTH_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_akap_response">WWAN_AUTH_AKAP_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_aka_response">WWAN_AUTH_AKA_RESPONSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_auth_method">WWAN_AUTH_METHOD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_sim_response">WWAN_AUTH_SIM_RESPONSE</a>

