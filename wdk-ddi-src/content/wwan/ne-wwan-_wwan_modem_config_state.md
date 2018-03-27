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




<a href="https://msdn.microsoft.com/3A13CFBC-DBB4-4BB1-ABA4-AB145AED07AA">WWAN_MODEM_CONFIG_STATUS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_MODEM_CONFIG_STATE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

