---
UID: NS:wlclient._DOT11_PORT_STATE
title: _DOT11_PORT_STATE
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_port_state.htm
old-project: netvista
ms.assetid: 09d36c81-d480-48c6-8633-c79061420217
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_PORT_STATE, *PDOT11_PORT_STATE, DOT11_PORT_STATE
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
req.alt-api: DOT11_PORT_STATE
req.alt-loc: wlclient.h
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
req.typenames: *PDOT11_PORT_STATE, DOT11_PORT_STATE
req.product: Windows 10 or later.
---

# _DOT11_PORT_STATE structure



## -description

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
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PORT_STATE structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

