---
UID: NE:wwan._WWAN_REGISTER_STATE
title: "_WWAN_REGISTER_STATE"
author: windows-driver-content
description: The WWAN_REGISTER_STATE enumeration lists the different provider network registration states that are supported by the MB device.
old-location: netvista\wwan_register_state.htm
old-project: netvista
ms.assetid: fba4e60e-c247-4466-9b0f-c8e7ffa594d2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/PWWAN_REGISTER_STATE, wwan/WwanRegisterStateSearching, wwan/WWAN_REGISTER_STATE, WwanRegisterStateDeregistered, wwan/WwanRegisterStateHome, WwanRegisterStateSearching, WwanRegisterStateMax, PWWAN_REGISTER_STATE enumeration pointer [Network Drivers Starting with Windows Vista], wwan/WwanRegisterStatePartner, WWAN_REGISTER_STATE enumeration [Network Drivers Starting with Windows Vista], wwan/WwanRegisterStateDeregistered, PWWAN_REGISTER_STATE, WwanRegisterStateRoaming, WWAN_REGISTER_STATE, WwanRegisterStateUnknown, wwan/WwanRegisterStateDenied, WwanRegisterStateDenied, WwanRef_927c04e0-b022-4d93-8052-696b5e9da51f.xml, WwanRegisterStatePartner, _WWAN_REGISTER_STATE, wwan/WwanRegisterStateRoaming, wwan/WwanRegisterStateUnknown, netvista.wwan_register_state, *PWWAN_REGISTER_STATE, WwanRegisterStateHome, wwan/WwanRegisterStateMax
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	WWAN_REGISTER_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_REGISTER_STATE, *PWWAN_REGISTER_STATE
req.product: Windows 10 or later.
---

# _WWAN_REGISTER_STATE enumeration


## -description


The WWAN_REGISTER_STATE enumeration lists the different provider network registration states that are
  supported by the MB device.


## -syntax


````
typedef enum _WWAN_REGISTER_STATE { 
  WwanRegisterStateUnknown       = 0,
  WwanRegisterStateDeregistered,
  WwanRegisterStateSearching,
  WwanRegisterStateHome,
  WwanRegisterStateRoaming,
  WwanRegisterStatePartner,
  WwanRegisterStateDenied,
  WwanRegisterStateMax
} WWAN_REGISTER_STATE, *PWWAN_REGISTER_STATE;
````


## -enum-fields




### -field WwanRegisterStateUnknown

The current registration state is unknown. The miniport driver may specify this state on a failure
     to set an appropriate 
     <i>WwanRegisterActionXxx</i>.


### -field WwanRegisterStateDeregistered

The device is not registered and is not searching for network providers.


### -field WwanRegisterStateSearching

The device is searching for a network provider.


### -field WwanRegisterStateHome

The device is using the home network provider.


### -field WwanRegisterStateRoaming

The device is using a network provider that supports roaming.


### -field WwanRegisterStatePartner

The device is using a roaming network partner.


### -field WwanRegisterStateDenied

Registration of the device on visible networks has been denied. However, emergency voice calls may
     still be made. This value applies only to voice connections, and not to data connections.


### -field WwanRegisterStateMax

The total number of supported registration states.


## -remarks


The current registration state is typically reflected in the device's user interface.

The 
    <b>WwanRegisterStatePartner</b> value indicates that the device is roaming on a preferred partner network,
    whereas 
    <b>WwanRegisterStateRoaming</b> value indicates that the device is just roaming. If the partner
    characterization of the roaming state is not available, the miniport driver should report 
    <b>WwanRegisterStateRoaming</b>.



## -see-also

<a href="..\wwan\ns-wwan-_wwan_registration_state.md">WWAN_REGISTRATION_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_REGISTER_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

