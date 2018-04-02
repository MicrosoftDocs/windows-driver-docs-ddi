---
UID: NE:wwan._WWAN_REGISTER_ACTION
title: "_WWAN_REGISTER_ACTION"
author: windows-driver-content
description: The WWAN_REGISTER_ACTION enumeration lists the different provider network registration actions that are supported by the MB device.
old-location: netvista\wwan_register_action.htm
old-project: netvista
ms.assetid: 8c343094-0927-4cdd-be39-93dcb25f6bf6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_REGISTER_ACTION, PWWAN_REGISTER_ACTION, PWWAN_REGISTER_ACTION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_REGISTER_ACTION, WWAN_REGISTER_ACTION enumeration [Network Drivers Starting with Windows Vista], WwanRef_27e66042-089c-435b-b255-d01e1ddebb5f.xml, WwanRegisterActionAutomatic, WwanRegisterActionManual, WwanRegisterActionMax, _WWAN_REGISTER_ACTION, netvista.wwan_register_action, wwan/PWWAN_REGISTER_ACTION, wwan/WWAN_REGISTER_ACTION, wwan/WwanRegisterActionAutomatic, wwan/WwanRegisterActionManual, wwan/WwanRegisterActionMax"
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
-	WWAN_REGISTER_ACTION
product: Windows
targetos: Windows
req.typenames: WWAN_REGISTER_ACTION, *PWWAN_REGISTER_ACTION
req.product: Windows 10 or later.
---

# _WWAN_REGISTER_ACTION enumeration


## -description


The WWAN_REGISTER_ACTION enumeration lists the different provider network registration actions that
  are supported by the MB device.


## -enum-fields




### -field WwanRegisterActionAutomatic

Automatically register with provider and then packet-attach, if required.


### -field WwanRegisterActionManual

Manually register with provider and then packet-attach, if required.


### -field WwanRegisterActionMax

The total number of supported registration actions.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571236">WWAN_SET_REGISTER_STATE</a>
 

 

