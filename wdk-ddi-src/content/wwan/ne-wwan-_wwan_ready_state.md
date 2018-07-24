---
UID: NE:wwan._WWAN_READY_STATE
title: "_WWAN_READY_STATE"
author: windows-driver-content
description: The WWAN_READY_STATE enumeration lists the different device ready-states that are supported by the MB device.
old-location: netvista\wwan_ready_state.htm
tech.root: netvista
ms.assetid: 46fec377-ba2c-469a-96be-23aa07079f8c
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: "*PWWAN_READY_STATE, PWWAN_READY_STATE, PWWAN_READY_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_READY_STATE, WWAN_READY_STATE enumeration [Network Drivers Starting with Windows Vista], WwanReadyStateBadSim, WwanReadyStateDeviceLocked, WwanReadyStateFailure, WwanReadyStateInitialized, WwanReadyStateNotActivated, WwanReadyStateOff, WwanReadyStateSimNotInserted, WwanRef_08468e16-e4da-49ff-9b2a-2cee4df6c72f.xml, _WWAN_READY_STATE, netvista.wwan_ready_state, wwan/PWWAN_READY_STATE, wwan/WWAN_READY_STATE, wwan/WwanReadyStateBadSim, wwan/WwanReadyStateDeviceLocked, wwan/WwanReadyStateFailure, wwan/WwanReadyStateInitialized, wwan/WwanReadyStateNotActivated, wwan/WwanReadyStateOff, wwan/WwanReadyStateSimNotInserted"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_READY_STATE
product:
- Windows
targetos: Windows
req.typenames: WWAN_READY_STATE, *PWWAN_READY_STATE
---

# _WWAN_READY_STATE enumeration


## -description


The WWAN_READY_STATE enumeration lists the different device ready-states that are supported by the MB
  device.


## -enum-fields




### -field WwanReadyStateOff

The device firmware stack is OFF or has not yet completed its initialization.


### -field WwanReadyStateInitialized

The device is ready to turn on and register with the provider.


### -field WwanReadyStateSimNotInserted

The SIM card is not inserted into the device.


### -field WwanReadyStateBadSim

The SIM card inserted into the device is invalid.


### -field WwanReadyStateFailure

A general device failure has occurred.


### -field WwanReadyStateNotActivated

The subscription is not activated.


### -field WwanReadyStateDeviceLocked

The device is locked and requires PIN1 or PUK1 to unlock.
     

Note that if a device is locked because it requires a PIN type other than PIN1 or PUK1 (for example,
     a network personalization PIN), miniport drivers should report 
     <b>WwanReadyStateInitialized</b>. Though miniport drivers should return WWAN_STATUS_PIN_REQUIRED for OID
     requests which are blocked because of PIN. Subsequent OID_WWAN_PIN 
     <i>query</i> requests should return the PIN type needed to unlock the device.


### -field WwanReadyStateNoEsimProfile


### -field WwanReadyStateMax




## -remarks



For devices that use a SIM card, this enumeration indicates if the SIM card has been initialized and
    is ready for access.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571226">WWAN_READY_INFO</a>
 

 

