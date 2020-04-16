---
UID: NS:bthddi._L2CAP_RETRANSMISSION_AND_FLOW_CONTROL
title: _L2CAP_RETRANSMISSION_AND_FLOW_CONTROL (bthddi.h)
description: The L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure describes configuration parameters for enhanced retransmission mode and streaming mode.
old-location: bltooth\l2cap_retransmission_and_flow_control.htm
tech.root: bltooth
ms.assetid: 0D4528C0-AEE6-4AD2-A3E6-524A6EB8A0D9
ms.date: 04/27/2018
keywords: ["_L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure"]
ms.keywords: "*PL2CAP_RETRANSMISSION_AND_FLOW_CONTROL, L2CAP_RETRANSMISSION_AND_FLOW_CONTROL, L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure [Bluetooth Devices], PL2CAP_RETRANSMISSION_AND_FLOW_CONTROL, PL2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure pointer [Bluetooth Devices], _L2CAP_RETRANSMISSION_AND_FLOW_CONTROL, bltooth.l2cap_retransmission_and_flow_control, bthddi/L2CAP_RETRANSMISSION_AND_FLOW_CONTROL, bthddi/PL2CAP_RETRANSMISSION_AND_FLOW_CONTROL"
f1_keywords:
 - "bthddi/L2CAP_RETRANSMISSION_AND_FLOW_CONTROL"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Bthddi.h
api_name:
- L2CAP_RETRANSMISSION_AND_FLOW_CONTROL
product:
- Windows
targetos: Windows
req.typenames: L2CAP_RETRANSMISSION_AND_FLOW_CONTROL, *PL2CAP_RETRANSMISSION_AND_FLOW_CONTROL
---

# _L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure


## -description


The L2CAP_RETRANSMISSION_AND_FLOW_CONTROL structure describes configuration parameters for enhanced retransmission mode and streaming mode.


## -struct-fields




### -field Mode

Requested mode for the enhanced L2CAP channel.


### -field TxWindowSize

Size of the transmission window for enhanced retransmission mode. The value of member is valid only when used with enhanced retransmission mode, and is ignored in streaming mode. Valid values range from 1 to 63.


### -field MaxTransmit

Number of times a single I/S frame will be re-transmitted in case of an error. The value of this member is valid only for enhanced retransmission mode and is ignored in streaming mode. The minimum value is 1.


### -field RetransmissionTO

Retransmission timeout value. Profile drivers should set this value to 0.


### -field MonitorTO

Monitor timeout. Profile drivers should set this value to 0.


### -field MaxPDUSize

Maximum PDU Size.

