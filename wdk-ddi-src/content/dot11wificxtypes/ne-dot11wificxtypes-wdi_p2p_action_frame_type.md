---
UID: NE:dot11wificxtypes._WDI_P2P_ACTION_FRAME_TYPE
tech.root: netvista
<<<<<<< HEAD
title: WDI_P2P_ACTION_FRAME_TYPE (dot11wificxtypes.h)
ms.date: 07/02/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_ACTION_FRAME_TYPE enum defines the Wi-Fi Direct action frame types.
=======
title: WDI_P2P_ACTION_FRAME_TYPE
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_P2P_ACTION_FRAME_TYPE enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_REQUEST

Wi-Fi Direct Group Owner Negotiation Request.

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_RESPONSE

Wi-Fi Direct Group Owner Negotiation Response.

### -field WDI_P2P_ACTION_FRAME_GO_NEGOTIATION_CONFIRM

Wi-Fi Direct Group Owner Negotiation Confirmation.

### -field WDI_P2P_ACTION_FRAME_INVITATION_REQUEST

Wi-Fi Direct Invitation Request.

### -field WDI_P2P_ACTION_FRAME_INVITATION_RESPONSE

Wi-Fi Direct Invitation Response.

### -field WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_REQUEST

Wi-Fi Direct Provision Discovery Request.

### -field WDI_P2P_ACTION_FRAME_PROVISION_DISCOVERY_RESPONSE

Wi-Fi Direct Provision Discovery Response.

### -field WDI_P2P_ACTION_FRAME_MAX_VALUE

## -remarks

The **WDI_P2P_ACTION_FRAME_TYPE** enum is a value in the [**WDI_TLV_P2P_SEND_ACTION_REQUEST_FRAME_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-send-action-request-frame-parameters) and [**WDI_TLV_P2P_ACTION_FRAME_RESPONSE_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-action-frame-response-parameters.md) TLVs.

## -see-also

[**WDI_TLV_P2P_SEND_ACTION_REQUEST_FRAME_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-send-action-request-frame-parameters)

[**WDI_TLV_P2P_ACTION_FRAME_RESPONSE_PARAMETERS**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-action-frame-response-parameters.md)