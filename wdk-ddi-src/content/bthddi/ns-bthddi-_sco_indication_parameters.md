---
UID: NS:bthddi._SCO_INDICATION_PARAMETERS
title: "_SCO_INDICATION_PARAMETERS" (bthddi.h)
description: The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification.
old-location: bltooth\sco_indication_parameters.htm
tech.root: bltooth
ms.assetid: 2d3ae219-8a40-476c-b8eb-94f4c0566527
ms.date: 04/27/2018
ms.keywords: "*PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS structure pointer [Bluetooth Devices], SCO_INDICATION_PARAMETERS, SCO_INDICATION_PARAMETERS structure [Bluetooth Devices], _SCO_INDICATION_PARAMETERS, bltooth.sco_indication_parameters, bth_structs_73ebf679-d092-4b0a-a54f-84539b8c85ae.xml, bthddi/PSCO_INDICATION_PARAMETERS, bthddi/SCO_INDICATION_PARAMETERS"
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	SCO_INDICATION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: SCO_INDICATION_PARAMETERS, *PSCO_INDICATION_PARAMETERS
---

# _SCO_INDICATION_PARAMETERS structure


## -description


The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or
  disconnect notification.


## -struct-fields




### -field ConnectionHandle

A connection handle to the remote device. This handle is only valid for notifications that arrive
     over an established SCO connection.


### -field BtAddress

The Bluetooth address of the remote device.


### -field Parameters



#### 


### -field Parameters.Connect

The structure that contains parameters for the 
      <b>ScoIndicationRemoteConnectSCO_INDICATION_CODE</b> event.


### -field Parameters.Connect.Request

The structure that contains the parameters for the SCO connection request.


### -field Parameters.Connect.Request.LinkType

A value from the 
        <a href="https://msdn.microsoft.com/library/windows/hardware/ff536781">SCO_LINK_TYPE</a> enumeration that indicates the
        type of incoming connection.


### -field Parameters.Disconnect

The structure that contains parameters for the 
      <b>ScoIndicationRemoteDisconnectSCO_INDICATION_CODE</b> event.


### -field Parameters.Disconnect.Reason

A 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff536775">SCO_DISCONNECT_REASON</a> value that
       indicates why the SCO connection was terminated.


### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver can set to indicate whether the SCO connection to the
       remote device will be closed. If the connection is to be closed, the value is <b>TRUE</b>. Otherwise, the
       value is <b>FALSE</b>.


## -remarks



A profile driver's 
    <a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a> should process
    a notification differently depending upon the value that the Bluetooth driver stack passes in the 
    <i>Indication</i> parameter of the callback function.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.

When the Bluetooth driver stack passes 
    <b>ScoIndicationRemoteDisconnect</b>, the callback function should use the 
    <b>Disconnect</b> member of the 
    <b>Parameters</b> union.




## -see-also




<a href="https://msdn.microsoft.com/abc9fc88-6852-4bfb-8271-7a73a508c397">SCO Callback Function</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536775">SCO_DISCONNECT_REASON</a>
 

 

