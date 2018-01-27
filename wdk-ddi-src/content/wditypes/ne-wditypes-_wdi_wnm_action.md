---
UID: NE:wditypes._WDI_WNM_ACTION
title: _WDI_WNM_ACTION
author: windows-driver-content
description: The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.
old-location: netvista\wdi_wnm_action.htm
old-project: netvista
ms.assetid: 350D3182-3BEE-4AB7-A9F0-5C5D7D60A617
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wdi_wnm_action, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, WDI_WNM_ACTION enumeration [Network Drivers Starting with Windows Vista], wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, WDI_WNM_ACTION, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, wditypes/WDI_WNM_ACTION, _WDI_WNM_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname: 
-	WDI_WNM_ACTION
product: Windows
targetos: Windows
req.typenames: WDI_WNM_ACTION
req.product: Windows 10 or later.
---

# _WDI_WNM_ACTION enumeration


## -description


The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.


## -syntax


````
typedef enum _WDI_WNM_ACTION { 
  WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY     = 6,
  WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST   = 7,
  WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE  = 8
} WDI_WNM_ACTION;
````


## -enum-fields




### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY

The message is a BSS Transition Management query frame.


### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST

The message is a BSS Transition Management request frame. This is sent by the AP to the client.


### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE

The message is a BSS Transition Management response frame. This is a response to the above request frame from the AP.

