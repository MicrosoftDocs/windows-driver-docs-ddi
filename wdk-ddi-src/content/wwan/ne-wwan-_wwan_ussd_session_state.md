---
UID: NE:wwan._WWAN_USSD_SESSION_STATE
title: "_WWAN_USSD_SESSION_STATE"
author: windows-driver-content
description: The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.
old-location: netvista\wwan_ussd_session_state.htm
old-project: netvista
ms.assetid: 5111A10F-F66F-4667-A77E-63691CCD282D
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wwan_ussd_session_state, *PWWAN_USSD_SESSION_STATE, wwan/WwanUssdSessionStateNew, wwan/WwanUssdSessionStateExisting, WWAN_USSD_SESSION_STATE enumeration [Network Drivers Starting with Windows Vista], wwan/WWAN_USSD_SESSION_STATE, WwanUssdSessionStateExisting, WWAN_USSD_SESSION_STATE, _WWAN_USSD_SESSION_STATE, WwanUssdSessionStateNew
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
-	WWAN_USSD_SESSION_STATE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_USSD_SESSION_STATE, WWAN_USSD_SESSION_STATE"
req.product: Windows 10 or later.
---

# _WWAN_USSD_SESSION_STATE enumeration


## -description


The WWAN_USSD_SESSION_STATE enumeration lists the different types of USSD session states.


## -syntax


````
typedef enum _WWAN_USSD_SESSION_STATE { 
  WwanUssdSessionStateNew       = 0,
  WwanUssdSessionStateExisting  = 1
} WWAN_USSD_SESSION_STATE;
````


## -enum-fields




### -field WwanUssdSessionStateNew

The USSD string is the first message of a USSD session.


### -field WwanUssdSessionStateExisting

The USSD string is not the first message of a USSD session.


## -remarks


Miniport drivers use the WWAN_USSD_SESSION_STATE enumeration to indicate whether a USSD string is the first message of a USSD session. Miniport drivers must use <i>WwanUssdSessionStateNew</i> for the first message of a network-initiated USSD session. Miniport drivers should use <i>WwanUssdSessionStateExisting</i> in all other cases.


