---
UID: NE:wditypes._WDI_WNM_ACTION
title: "_WDI_WNM_ACTION"
author: windows-driver-content
description: The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.
old-location: netvista\wdi_wnm_action.htm
tech.root: netvista
ms.assetid: 350D3182-3BEE-4AB7-A9F0-5C5D7D60A617
ms.date: 5/2/2018
ms.keywords: WDI_WNM_ACTION, WDI_WNM_ACTION enumeration [Network Drivers Starting with Windows Vista], WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE, _WDI_WNM_ACTION, netvista.wdi_wnm_action, wditypes/WDI_WNM_ACTION, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST, wditypes/WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_WNM_ACTION
product:
- Windows
targetos: Windows
req.typenames: WDI_WNM_ACTION
---

# _WDI_WNM_ACTION enumeration


## -description


The WDI_WNM_ACTION enumeration defines the message type for 802.11v BSS Transition Management action frames.


## -enum-fields




### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_QUERY

The message is a BSS Transition Management query frame.


### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_REQUEST

The message is a BSS Transition Management request frame. This is sent by the AP to the client.


### -field WDI_WNM_ACTION_BSS_TRANSITION_MANAGEMENT_RESPONSE

The message is a BSS Transition Management response frame. This is a response to the above request frame from the AP.

