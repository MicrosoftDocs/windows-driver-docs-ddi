---
UID: NE:wwan._WWAN_ACTIVATION_COMMAND
title: _WWAN_ACTIVATION_COMMAND (wwan.h)
description: The WWAN_ACTIVATION_COMMAND enumeration lists the Packet Data Protocol (PDP) activation commands that are supported by the MB device.
old-location: netvista\wwan_activation_command.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_ACTIVATION_COMMAND enumeration"]
ms.keywords: "*PWWAN_ACTIVATION_COMMAND, PWWAN_ACTIVATION_COMMAND, PWWAN_ACTIVATION_COMMAND enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_ACTIVATION_COMMAND, WWAN_ACTIVATION_COMMAND enumeration [Network Drivers Starting with Windows Vista], WwanActivationCommandActivate, WwanActivationCommandDeactivate, WwanActivationCommandMax, WwanRef_55137856-bb05-49ac-b318-cc6922a90445.xml, _WWAN_ACTIVATION_COMMAND, netvista.wwan_activation_command, wwan/PWWAN_ACTIVATION_COMMAND, wwan/WWAN_ACTIVATION_COMMAND, wwan/WwanActivationCommandActivate, wwan/WwanActivationCommandDeactivate, wwan/WwanActivationCommandMax"
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
targetos: Windows
req.typenames: WWAN_ACTIVATION_COMMAND, *PWWAN_ACTIVATION_COMMAND
f1_keywords:
 - _WWAN_ACTIVATION_COMMAND
 - wwan/_WWAN_ACTIVATION_COMMAND
 - PWWAN_ACTIVATION_COMMAND
 - wwan/PWWAN_ACTIVATION_COMMAND
 - WWAN_ACTIVATION_COMMAND
 - wwan/WWAN_ACTIVATION_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_ACTIVATION_COMMAND
---

# _WWAN_ACTIVATION_COMMAND enumeration


## -description

The WWAN_ACTIVATION_COMMAND enumeration lists the Packet Data Protocol (PDP) activation commands that
  are supported by the MB device.

## -enum-fields

### -field WwanActivationCommandDeactivate

Deactivate a currently activated PDP context identified by 
     <b>ConnectionId</b> .

### -field WwanActivationCommandActivate

Activate PDP context.

### -field WwanActivationCommandMax

The total number of supported activation commands.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_set_context_state">WWAN_SET_CONTEXT_STATE</a>
