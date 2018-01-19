---
UID: NE:wwan._WWAN_REGISTER_ACTION
title: _WWAN_REGISTER_ACTION
author: windows-driver-content
description: The WWAN_REGISTER_ACTION enumeration lists the different provider network registration actions that are supported by the MB device.
old-location: netvista\wwan_register_action.htm
old-project: netvista
ms.assetid: 8c343094-0927-4cdd-be39-93dcb25f6bf6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WWAN_REGISTER_ACTION, *PWWAN_REGISTER_ACTION, WWAN_REGISTER_ACTION
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
req.alt-api: WWAN_REGISTER_ACTION
req.alt-loc: wwan.h
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
req.typenames: *PWWAN_REGISTER_ACTION, WWAN_REGISTER_ACTION
req.product: Windows 10 or later.
---

# _WWAN_REGISTER_ACTION enumeration



## -description
The WWAN_REGISTER_ACTION enumeration lists the different provider network registration actions that
  are supported by the MB device.



## -syntax

````
typedef enum _WWAN_REGISTER_ACTION { 
  WwanRegisterActionAutomatic  = 0,
  WwanRegisterActionManual,
  WwanRegisterActionMax
} WWAN_REGISTER_ACTION, *PWWAN_REGISTER_ACTION;
````


## -enum-fields

### -field WwanRegisterActionAutomatic

Automatically register with provider and then packet-attach, if required.


### -field WwanRegisterActionManual

Manually register with provider and then packet-attach, if required.


### -field WwanRegisterActionMax

The total number of supported registration actions.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan-_wwan_set_register_state.md">WWAN_SET_REGISTER_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_REGISTER_ACTION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

