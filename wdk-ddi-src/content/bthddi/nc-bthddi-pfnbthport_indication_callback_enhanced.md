---
UID: NC:bthddi.PFNBTHPORT_INDICATION_CALLBACK_ENHANCED
title: PFNBTHPORT_INDICATION_CALLBACK_ENHANCED
author: windows-driver-content
description: Profile drivers implement an enhanced L2CAP callback function to provide the Bluetooth driver stack with a mechanism to notify the profile driver about any changes to the status of a currently open L2CAP or eL2CAP connection.
old-location: bltooth\enhanced_l2cap_callback_function.htm
old-project: bltooth
ms.assetid: 1C08937A-2B0C-4A6C-ACDF-1A751BF0D6F6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BluetoothPortIndicationCallbackEnhanced, BluetoothPortIndicationCallbackEnhanced callback function [Bluetooth Devices], PFNBTHPORT_INDICATION_CALLBACK_ENHANCED, bltooth.enhanced_l2cap_callback_function, bthddi/BluetoothPortIndicationCallbackEnhanced
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 8 and later versions of Windows.
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
-	UserDefined
api_location:
-	bthddi.h
api_name:
-	BluetoothPortIndicationCallbackEnhanced
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# PFNBTHPORT_INDICATION_CALLBACK_ENHANCED callback


## -description


Profile drivers implement an enhanced L2CAP callback function to provide the Bluetooth driver stack with a
  mechanism to notify the profile driver about any changes to the status of a currently open L2CAP or eL2CAP connection.


## -prototype


````
PFNBTHPORT_INDICATION_CALLBACK_ENHANCED BluetoothPortIndicationCallbackEnhanced;

VOID WINAPI BluetoothPortIndicationCallbackEnhanced(
  _In_ PVOID                           Context,
  _In_ INDICATION_CODE                 Indication,
  _In_ PINDICATION_PARAMETERS_ENHANCED Parameters
)
{ ... }
````


## -parameters




### -param Context [in]

For
     changes to existing L2CAP connections, this is the 
     <b>CallbackContext</b> member specified by the profile driver when it built and sent a 
     <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_enhanced_channel.md">_BRB_L2CA_OPEN_ENHANCED_CHANNEL</a> structure.


### -param Indication [in]

An 
     <a href="..\bthddi\ne-bthddi-_indication_code.md">INDICATION_CODE</a> value that indicates the type
     of L2CAP event.


### -param Parameters [in]

An 
     <a href="..\bthddi\ns-bthddi-_indication_parameters_enhanced.md">INDICATION_PARAMETERS_ENHANCED</a> structure that
     contains event-specific parameters.


## -returns



None




## -remarks



A profile driver registers its L2CAP or eL2CAP callback function by specifying the callback function in the 
      <b>Callback</b> member of the _BRB_L2CA_OPEN_ENHANCED_CHANNEL structure when the profile driver attempts to connect to a remote device using the
      BRB_L2CA_OPEN_ENHANCED_CHANNEL or BRB_L2CA_OPEN_ENHANCED_CHANNEL_RESPONSE BRBs.

After the profile driver registers its L2CAP callback function, the callback function is only
    associated with the enhanced channel that the BRB opened. The Bluetooth driver stack can call the L2CAP callback
    function to notify the profile driver of actions that occur over the open enhanced channel to the remote device.
    Profile drivers can register a single callback function to handle L2CAP channel notifications as a client.

The 
    <a href="..\bthddi\ns-bthddi-_indication_parameters_enhanced.md">INDICATION_PARAMETERS_ENHANCED</a> structure held in
    the 
    <i>Parameters</i> parameter is interpreted according to the value of the 
    <a href="..\bthddi\ne-bthddi-_indication_code.md">INDICATION_CODE</a> enumeration that the Bluetooth
    driver stack passes to the profile driver's enhanced L2CAP callback function through the 
    <i>Indication</i> parameter. For most notifications, there is an INDICATION_PARAMETERS_ENHANCED union member that
    corresponds to the event and contains event-specific parameters.



