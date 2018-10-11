---
UID: NS:wlclient._DOT11_PORT_STATE
title: "_DOT11_PORT_STATE"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_port_state.htm
tech.root: netvista
ms.assetid: 09d36c81-d480-48c6-8633-c79061420217
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_PORT_STATE, DOT11_PORT_STATE, DOT11_PORT_STATE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_679b7f27-efba-43e8-9d20-7047c770b7db.xml, PDOT11_PORT_STATE, PDOT11_PORT_STATE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PORT_STATE, netvista.dot11_port_state, wlclient/DOT11_PORT_STATE, wlclient/PDOT11_PORT_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlclient.h
req.include-header: Wlclient.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	wlclient.h
api_name:
-	DOT11_PORT_STATE
product:
- Windows
targetos: Windows
req.typenames: DOT11_PORT_STATE, *PDOT11_PORT_STATE
req.product: Windows 10 or later.
---

# _DOT11_PORT_STATE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PORT_STATE structure defines the port state for a security session with a peer within a
  basic service set (BSS) network. The peer could either be an access point (AP) within an infrastructure BSS
  network, or a peer station within an independent BSS (IBSS) network.


## -syntax


````
typedef struct _DOT11_PORT_STATE {
  DOT11_MAC_ADDRESS PeerMacAddress;
  ULONG             uSessionId;
  BOOL              bPortControlled;
  BOOL              bPortAuthorized;
} DOT11_PORT_STATE, *PDOT11_PORT_STATE;
````


## -struct-fields




### -field PeerMacAddress

The media access control (MAC) address of the AP or peer station with which the security session
     has been initiated.


### -field uSessionId

The security session identifier (ID) assigned by the operating system.


### -field bPortControlled

A Boolean value that defines whether the port is controlled for access to the BSS network. A value
     of <b>TRUE</b> specifies that the port has controlled access to the network.


For more information about controlled and uncontrolled port access, refer to Clause 6.3 of the IEEE
     802.1X-1999 standard.


### -field bPortAuthorized

A Boolean value that defines whether the port is authorized to access the BSS network. A value of
     <b>TRUE</b> specifies that the port has been authorized for network access.


For more information about authorized port access, refer to Clause 6.3 of the IEEE 802.1X-1999
     standard.


## -remarks



The operating system passes in the current port state of the security session through the
    <i>pPortState</i> parameter of the
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
    Dot11ExtIhvPerformPostAssociate</a> IHV handler function. When this function is called, the IHV
    Extensions DLL must not change the data referenced by the
    <i>pPortState</i> parameter.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



 

 


