---
UID: NE:wwan._WWAN_USSD_SESSION_STATE
title: _WWAN_USSD_SESSION_STATE (wwan.h)
description: The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.
old-location: netvista\wwan_ussd_session_state.htm
tech.root: netvista
ms.assetid: 5111A10F-F66F-4667-A77E-63691CCD282D
ms.date: 05/02/2018
ms.keywords: "*PWWAN_USSD_SESSION_STATE, WWAN_USSD_SESSION_STATE, WWAN_USSD_SESSION_STATE enumeration [Network Drivers Starting with Windows Vista], WwanUssdSessionStateExisting, WwanUssdSessionStateNew, _WWAN_USSD_SESSION_STATE, netvista.wwan_ussd_session_state, wwan/WWAN_USSD_SESSION_STATE, wwan/WwanUssdSessionStateExisting, wwan/WwanUssdSessionStateNew"
ms.topic: enum
f1_keywords:
 - "wwan/WWAN_USSD_SESSION_STATE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_USSD_SESSION_STATE
product:
- Windows
targetos: Windows
req.typenames: WWAN_USSD_SESSION_STATE, *PWWAN_USSD_SESSION_STATE
---

# _WWAN_USSD_SESSION_STATE enumeration


## -description


The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.


## -enum-fields




### -field WwanUssdSessionStateNew

The USSD string is the first message of a USSD session.


### -field WwanUssdSessionStateExisting

The USSD string is not the first message of a USSD session.


## -remarks



Miniport drivers use the WWAN_USSD_SESSION_STATE enumeration to indicate whether a USSD string is the first message of a USSD session. Miniport drivers must use <i>WwanUssdSessionStateNew</i> for the first message of a network-initiated USSD session. Miniport drivers should use <i>WwanUssdSessionStateExisting</i> in all other cases.



