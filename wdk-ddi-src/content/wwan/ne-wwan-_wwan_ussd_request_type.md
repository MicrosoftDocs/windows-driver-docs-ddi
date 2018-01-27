---
UID: NE:wwan._WWAN_USSD_REQUEST_TYPE
title: _WWAN_USSD_REQUEST_TYPE
author: windows-driver-content
description: The WWAN_USSD_REQUEST_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) session requests.
old-location: netvista\wwan_ussd_request_type.htm
old-project: netvista
ms.assetid: 773490EE-ECFC-4089-869D-19683A76E4FA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WwanUssdRequestCancel, WwanUssdRequestInitiate, wwan/WwanUssdRequestInitiate, WWAN_USSD_REQUEST_TYPE, *PWWAN_USSD_REQUEST_TYPE, wwan/WwanUssdRequestContinue, wwan/WWAN_USSD_REQUEST_TYPE, wwan/WwanUssdRequestCancel, WWAN_USSD_REQUEST_TYPE enumeration [Network Drivers Starting with Windows Vista], _WWAN_USSD_REQUEST_TYPE, WwanUssdRequestContinue, netvista.wwan_ussd_request_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wwan.h
apiname: 
-	WWAN_USSD_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: *PWWAN_USSD_REQUEST_TYPE, WWAN_USSD_REQUEST_TYPE
req.product: Windows 10 or later.
---

# _WWAN_USSD_REQUEST_TYPE enumeration


## -description


The WWAN_USSD_REQUEST_TYPE enumeration lists the different types of Unstructured Supplementary Service Data (USSD) session requests.


## -syntax


````
typedef enum _WWAN_USSD_REQUEST_TYPE { 
  WwanUssdRequestInitiate  = 0,
  WwanUssdRequestContinue  = 1,
  WwanUssdRequestCancel    = 2
} WWAN_USSD_REQUEST_TYPE;
````


## -enum-fields




### -field WwanUssdRequestInitiate

Indicates a request to create a new USSD session and to transmit the accompanying USSD string.


### -field WwanUssdRequestContinue

Indicates a request to send the accompanying USSD string using the existing USSD session.


### -field WwanUssdRequestCancel

Indicates a request to terminate the existing USSD session.


## -remarks


The USSD protocol only allows a single USSD session at any time. If the miniport driver receives a <i>WwanUssdRequestInitiate</i> request to create a new USSD session when one already exists, the miniport driver must fail the request and specify <i>WwanUssdEventOtherLocalClient</i> as the reason.

When responding to a <i>WwanUssdRequestCancel</i> request, miniport drivers must return <i>WwanUssdEventTerminated</i> as the reason even if no session existed (which may happen during a concurrent release of the session from the network and the local client). The content of the accompanying USSD string must be ignored for WwanUssdRequestCancel requests and the string length should be set to zero to indicate that there is no accompanying USSD string.


