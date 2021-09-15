---
UID: NE:dot11wificxtypes._WDI_P2P_ACTION_FRAME_TYPE
tech.root: netvista
title: WDI_P2P_ACTION_FRAME_TYPE (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_ACTION_FRAME_TYPE enum defines the Wi-Fi Direct action frame types.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_P2P_ACTION_FRAME_TYPE
 - WDI_P2P_ACTION_FRAME_TYPE
f1_keywords:
 - _WDI_P2P_ACTION_FRAME_TYPE
 - dot11wificxtypes/_WDI_P2P_ACTION_FRAME_TYPE
 - WDI_P2P_ACTION_FRAME_TYPE
 - dot11wificxtypes/WDI_P2P_ACTION_FRAME_TYPE
dev_langs:
 - c++
---

## -description

The **WDI_P2P_ACTION_FRAME_TYPE** enumeration defines the Wi-Fi Direct action frame types.

## -enum-fields

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_REQUEST:1

Wi-Fi Direct Group Owner Negotiation Request.

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_RESPONSE:2

Wi-Fi Direct Group Owner Negotiation Response.

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_CONFIRM:3

Wi-Fi Direct Group Owner Negotiation Confirmation.

### -field WDI_P2P_ACTION_FRAME_INVITATION_REQUEST:4

Wi-Fi Direct Invitation Request.

### -field WDI_P2P_ACTION_FRAME_INVITATION_RESPONSE:5

Wi-Fi Direct Invitation Response.

### -field WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_REQUEST:6

Wi-Fi Direct Provision Discovery Request.

### -field WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_RESPONSE:7

Wi-Fi Direct Provision Discovery Response.

### -field WDI_P2P_ACTION_FRAME_MAX_VALUE:0xFFFFFFFF

## -remarks

The **WDI_P2P_ACTION_FRAME_TYPE** enum is a value in the [**WDI_TLV_P2P_SEND_ACTION_REQUEST_FRAME_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-send-action-request-frame-parameters) and [**WDI_TLV_P2P_ACTION_FRAME_RESPONSE_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-action-frame-response-parameters.md) TLVs.

## -see-also

[**WDI_TLV_P2P_SEND_ACTION_REQUEST_FRAME_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-send-action-request-frame-parameters)

[**WDI_TLV_P2P_ACTION_FRAME_RESPONSE_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-action-frame-response-parameters.md)