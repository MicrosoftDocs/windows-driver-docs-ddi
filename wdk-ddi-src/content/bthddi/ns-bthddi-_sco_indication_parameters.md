---
UID: NS:bthddi._SCO_INDICATION_PARAMETERS
title: _SCO_INDICATION_PARAMETERS (bthddi.h)
description: The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification.
old-location: bltooth\sco_indication_parameters.htm
tech.root: bltooth
ms.date: 05/12/2021
keywords: ["SCO_INDICATION_PARAMETERS structure"]
ms.keywords: "*PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS, PSCO_INDICATION_PARAMETERS structure pointer [Bluetooth Devices], SCO_INDICATION_PARAMETERS, SCO_INDICATION_PARAMETERS structure [Bluetooth Devices], _SCO_INDICATION_PARAMETERS, bltooth.sco_indication_parameters, bth_structs_73ebf679-d092-4b0a-a54f-84539b8c85ae.xml, bthddi/PSCO_INDICATION_PARAMETERS, bthddi/SCO_INDICATION_PARAMETERS"
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
targetos: Windows
req.typenames: SCO_INDICATION_PARAMETERS, *PSCO_INDICATION_PARAMETERS
f1_keywords:
 - _SCO_INDICATION_PARAMETERS
 - bthddi/_SCO_INDICATION_PARAMETERS
 - PSCO_INDICATION_PARAMETERS
 - bthddi/PSCO_INDICATION_PARAMETERS
 - SCO_INDICATION_PARAMETERS
 - bthddi/SCO_INDICATION_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthddi.h
api_name:
 - _SCO_INDICATION_PARAMETERS
 - PSCO_INDICATION_PARAMETERS
 - SCO_INDICATION_PARAMETERS
---

# _SCO_INDICATION_PARAMETERS structure

## -description

The SCO_INDICATION_PARAMETERS structure describes indication parameters about a SCO connect or disconnect notification.

## -struct-fields

### -field ConnectionHandle

A connection handle to the remote device. This handle is only valid for notifications that arrive over an established SCO connection.

### -field BtAddress

The Bluetooth address of the remote device.

### -field Parameters

Union of the following fields.

### -field Parameters.Connect

The structure that contains parameters for the **ScoIndicationRemoteConnectSCO_INDICATION_CODE** event.

### -field Parameters.Connect.Request

The structure that contains the parameters for the SCO connection request.

### -field Parameters.Connect.Request.LinkType

A value from the [SCO\_LINK\_TYPE](/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_link_type) enumeration that indicates the type of incoming connection.

### -field Parameters.Disconnect

The structure that contains parameters for the **ScoIndicationRemoteDisconnectSCO_INDICATION_CODE** event.

### -field Parameters.Disconnect.Reason

A [SCO\_DISCONNECT\_REASON](/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_disconnect_reason) value that indicates why the SCO connection was terminated.

### -field Parameters.Disconnect.CloseNow

A Boolean value that a profile driver can set to indicate whether the SCO connection to the remote device will be closed. If the connection is to be closed, the value is **TRUE**. Otherwise, the value is **FALSE**.

## -remarks

A profile driver's [SCO Callback Function](/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnsco_indication_callback) should process a notification differently depending upon the value that the Bluetooth driver stack passes in the *Indication* parameter of the callback function.

When the Bluetooth driver stack passes **ScoIndicationRemoteConnect**, the callback function should use the **Connect** member of the **Parameters** union.

When the Bluetooth driver stack passes **ScoIndicationRemoteDisconnect**, the callback function should use the **Disconnect** member of the **Parameters** union.

## -see-also

[SCO Callback Function](/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnsco_indication_callback)

[SCO\_DISCONNECT\_REASON](/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_sco_disconnect_reason)
