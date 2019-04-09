---
UID: NE:wditypes._WDI_P2P_LISTEN_STATE
title: _WDI_P2P_LISTEN_STATE (wditypes.h)
description: The WDI_P2P_LISTEN_STATE enumeration defines the Wi-Fi Direct listen states.
old-location: netvista\wdi_p2p_listen_state.htm
tech.root: netvista
ms.assetid: 68798F3D-B708-4DCD-AB3F-D8DE4A8A0CF2
ms.date: 05/02/2018
ms.keywords: WDI_P2P_LISTEN_STATE, WDI_P2P_LISTEN_STATE enumeration [Device and Driver Installation], WDI_P2P_LISTEN_STATE_AUTOMATIC_AVAILABILITY, WDI_P2P_LISTEN_STATE_HIGH_AVAILABILITY, WDI_P2P_LISTEN_STATE_OFF, WDI_P2P_LISTEN_STATE_PASSIVE_AVAILABILITY, _WDI_P2P_LISTEN_STATE, netvista.wdi_p2p_listen_state, netvista.wifi_p2p_listen_state, wditypes/WDI_P2P_LISTEN_STATE, wditypes/WDI_P2P_LISTEN_STATE_AUTOMATIC_AVAILABILITY, wditypes/WDI_P2P_LISTEN_STATE_HIGH_AVAILABILITY, wditypes/WDI_P2P_LISTEN_STATE_OFF, wditypes/WDI_P2P_LISTEN_STATE_PASSIVE_AVAILABILITY
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wditypes.hpp
api_name:
- WDI_P2P_LISTEN_STATE
product:
- Windows
targetos: Windows
req.typenames: WDI_P2P_LISTEN_STATE
---

# _WDI_P2P_LISTEN_STATE enumeration


## -description


The WDI_P2P_LISTEN_STATE enumeration defines the Wi-Fi Direct listen states.


## -enum-fields




### -field WDI_P2P_LISTEN_STATE_OFF

When this listen state is set:

<ul>
<li>The port shall not schedule any time to explicitly listen on social channels for incoming Wi-Fi Direct action frames.</li>
<li>The port shall not respond to probe requests as a Wi-Fi Direct Adapter.</li>
</ul>

### -field WDI_P2P_LISTEN_STATE_PASSIVE_AVAILABILITY

When this listen state is set:

<ul>
<li>The port must enter into listen state periodically as specified by the ListenDuration parameters.</li>
<li>The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the specified channel.</li>
</ul>

### -field WDI_P2P_LISTEN_STATE_AUTOMATIC_AVAILABILITY

When this listen state is set:

<ul>
<li>The port must schedule time to explicitly listen on a social channel for incoming Wi-Fi Direct action frames.</li>
<li>The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the configured social channel.</li>
</ul>
<div class="alert"><b>Note</b>  The optimized duty cycle for automatic availability listen state is outside the scope of this specification. The most aggressive power saving schedule that may be implemented by the port is being available for a contiguous 500ms out of every 5 seconds.</div>
<div> </div>

### -field WDI_P2P_LISTEN_STATE_HIGH_AVAILABILITY

When this listen state is set:

<ul>
<li>The port must schedule time to explicitly listen on a social channel for incoming Wi-Fi Direct action frames.</li>
<li>The port shall respond to probe requests with a "DIRECT-" SSID as a Wi-Fi Direct Adapter when parked on the configured social channel.</li>
</ul>
<div class="alert"><b>Note</b>  The duty cycle for this listen state is 300ms availability every 400ms on the configured social channel.</div>
<div> </div>

### -field WDI_P2P_LISTEN_STATE_DUMMY_MAX_VALUE



