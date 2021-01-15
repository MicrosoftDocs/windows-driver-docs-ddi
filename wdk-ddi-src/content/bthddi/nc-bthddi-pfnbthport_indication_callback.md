---
UID: NC:bthddi.PFNBTHPORT_INDICATION_CALLBACK
title: PFNBTHPORT_INDICATION_CALLBACK (bthddi.h)
description: Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and any changes to the status of a currently open L2CAP connection.
old-location: bltooth\l2cap_callback_function.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["PFNBTHPORT_INDICATION_CALLBACK callback function"]
ms.keywords: BluetoothPortIndicationCallback, BluetoothPortIndicationCallback callback function [Bluetooth Devices], PFNBTHPORT_INDICATION_CALLBACK, PFNBTHPORT_INDICATION_CALLBACK callback, bltooth.l2cap_callback_function, bth_funcs_76d9cb39-ead0-4465-9cc5-83b559b0ba55.xml, bthddi/BluetoothPortIndicationCallback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNBTHPORT_INDICATION_CALLBACK
 - bthddi/PFNBTHPORT_INDICATION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - bthddi.h
api_name:
 - PFNBTHPORT_INDICATION_CALLBACK
---

# PFNBTHPORT_INDICATION_CALLBACK callback function


## -description

Profile drivers implement a L2CAP callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about incoming L2CAP connection requests from remote devices, and
  any changes to the status of a currently open L2CAP connection.

## -parameters

### -param Context 

[in]
For incoming remote connection request indications, this is the context specified by the profile
     driver in the 
     <b>IndicationCallbackContext</b> member of the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">
     _BRB_L2CA_REGISTER_SERVER</a> structure when the profile driver registered the callback function. For
     changes to existing L2CAP connections, this is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a> BRB.

### -param Indication 

[in]
An 
     <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a> value that indicates the type
     of L2CAP event.

### -param Parameters 

[in]
An 
     <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a> structure that
     contains event-specific parameters.

## -remarks

A profile driver registers its L2CAP callback function in the following two scenarios:

<ol>
<li>
When a profile driver acts as a server, it registers a L2CAP callback function using the 
      <b>IndicationCallback</b> member of the 
      <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">
      _BRB_L2CA_REGISTER_SERVER</a> structure. The Bluetooth driver stack can then notify the profile
      driver when a remote device attempts to contact it.

</li>
<li>
When the profile driver acts as a client and attempts to connect to a remote device using the
      <b>BRB_L2CA_OPEN_CHANNEL</b> BRB, the profile driver registers its L2CAP callback function using the 
      <b>Callback</b> member of the _BRB_L2CA_OPEN_CHANNEL structure that is passed when the profile driver 
      <a href="/previous-versions/ff536657(v=vs.85)">builds and sends</a> a 
      <a href="/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> or 
      <a href="/previous-versions/ff536616(v=vs.85)">
      BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request.

</li>
</ol>
After the profile driver registers its L2CAP callback function, the callback function is only
    associated with the channel that the BRB opened. The Bluetooth driver stack can call the L2CAP callback
    function to notify the profile driver of actions that occur over the open channel to the remote device.
    Profile drivers can register a single callback function to handle channel notifications as a client and
    connection notifications as a server.

The 
    <a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a> structure held in
    the 
    <i>Parameters</i> parameter is interpreted according to the value of the 
    <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a> enumeration that the Bluetooth
    driver stack passes to the profile driver's L2CAP callback function through the 
    <i>Indication</i> parameter. For most notifications, there is an INDICATION_PARAMETERS union member that
    corresponds to the event and contains event-specific parameters.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_indication_code">INDICATION_CODE</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_indication_parameters">INDICATION_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>



<a href="/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_register_server">_BRB_L2CA_REGISTER_SERVER</a>

