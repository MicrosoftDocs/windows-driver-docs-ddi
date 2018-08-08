---
UID: NE:wditypes._WDI_STOP_AP_REASON
title: "_WDI_STOP_AP_REASON"
author: windows-driver-content
description: The WDI_STOP_AP_REASON enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.
old-location: netvista\wdi_stop_ap_reason.htm
tech.root: netvista
ms.assetid: F0CACC25-2F7B-431A-8AAB-CBE495178CC1
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: WDI_STOP_AP_REASON, WDI_STOP_AP_REASON enumeration [Network Drivers Starting with Windows Vista], WDI_STOP_AP_REASON_AP_ACTIVE, WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE, WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE, WDI_STOP_AP_REASON_IHV_END, WDI_STOP_AP_REASON_IHV_START, _WDI_STOP_AP_REASON, netvista.wdi_stop_ap_reason, wditypes/WDI_STOP_AP_REASON, wditypes/WDI_STOP_AP_REASON_AP_ACTIVE, wditypes/WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE, wditypes/WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE, wditypes/WDI_STOP_AP_REASON_IHV_END, wditypes/WDI_STOP_AP_REASON_IHV_START
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_STOP_AP_REASON
product:
- Windows
targetos: Windows
req.typenames: WDI_STOP_AP_REASON
---

# _WDI_STOP_AP_REASON enumeration


## -description


The WDI_STOP_AP_REASON enumeration defines the reasons an adapter cannot sustain 802.11 Access Point (AP) functionality on any of the PHYs.


## -enum-fields




### -field WDI_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE

The adapter determined that no valid operating frequency is available.


### -field WDI_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE

The adapter determined that no operating channel is available.


### -field WDI_STOP_AP_REASON_AP_ACTIVE

The adapter determined that an AP is already active on another 802.11 MAC entity for this physical wireless LAN adapter.


### -field WDI_STOP_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.


### -field WDI_STOP_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.

