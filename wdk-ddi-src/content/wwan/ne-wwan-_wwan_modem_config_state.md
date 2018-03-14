---
UID: NE:wwan._WWAN_MODEM_CONFIG_STATE
title: "_WWAN_MODEM_CONFIG_STATE"
author: windows-driver-content
description: The WWAN_MODEM_CONFIG_STATE enumeration lists definitions used by the modem to inform the OS about its modem configuration state.
old-location: netvista\wwan_modem_config_state.htm
old-project: netvista
ms.assetid: A22EA7A7-2C28-4117-A2B8-A7D3D4C9F11B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_MODEM_CONFIG_STATE, PWWAN_MODEM_CONFIG_STATE, PWWAN_MODEM_CONFIG_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_MODEM_CONFIG_STATE, WWAN_MODEM_CONFIG_STATE enumeration [Network Drivers Starting with Windows Vista], WwanModemConfigStateActivated, WwanModemConfigStateMax, WwanModemConfigStatePending, WwanModemConfigStateUnknown, _WWAN_MODEM_CONFIG_STATE, netvista.wwan_modem_config_state, wwan/PWWAN_MODEM_CONFIG_STATE, wwan/WWAN_MODEM_CONFIG_STATE, wwan/WwanModemConfigStateActivated, wwan/WwanModemConfigStateMax, wwan/WwanModemConfigStatePending, wwan/WwanModemConfigStateUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_MODEM_CONFIG_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_MODEM_CONFIG_STATE, *PWWAN_MODEM_CONFIG_STATE
req.product: Windows 10 or later.
---

# _WWAN_MODEM_CONFIG_STATE enumeration


## -description


The <b>WWAN_MODEM_CONFIG_STATE</b> enumeration lists definitions used by the modem to inform the OS about its modem configuration state.


## -syntax


````
typedef enum _WWAN_MODEM_CONFIG_STATE { 
  WwanModemConfigStateUnknown    = 0,
  WwanModemConfigStatePending,
  WwanModemConfigStateActivated,
  WwanModemConfigStateMax
} WWAN_MODEM_CONFIG_STATE, *PWWAN_MODEM_CONFIG_STATE;
````


## -enum-fields




### -field WwanModemConfigStateUnknown

The modem configuration state is currently not available.


### -field WwanModemConfigStatePending

The modem is currently selecting the best suitable configuration file that matches the UICC info.


### -field WwanModemConfigStateActivated

The modem has completed its configuration and modem subcomponents are aware of the new configuration.


### -field WwanModemConfigStateMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_modem_config_status.md">WWAN_MODEM_CONFIG_STATUS</a>



 

 


