---
UID: NE:dot11wificxtypes._WDI_CAN_SUSTAIN_AP_REASON
tech.root: netvista
<<<<<<< HEAD
title: WDI_CAN_SUSTAIN_AP_REASON (dot11wificxtypes.h)
ms.date: 08/05/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CAN_SUSTAIN_AP_REASON enum defines the reasons the port is ready to receive a OID_WDI_TASK_START_AP request.
=======
title: WDI_CAN_SUSTAIN_AP_REASON
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_CAN_SUSTAIN_AP_REASON enumeration for internal use only. Don't use this enumeration in your code."
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
 - _WDI_CAN_SUSTAIN_AP_REASON
 - WDI_CAN_SUSTAIN_AP_REASON
f1_keywords:
 - _WDI_CAN_SUSTAIN_AP_REASON
 - dot11wificxtypes/_WDI_CAN_SUSTAIN_AP_REASON
 - WDI_CAN_SUSTAIN_AP_REASON
 - dot11wificxtypes/WDI_CAN_SUSTAIN_AP_REASON
dev_langs:
 - c++
---

## -description

The WDI_CAN_SUSTAIN_AP_REASON enumeration defines the reasons the port is ready to receive a [OID_WDI_TASK_START_AP](/windows-hardware/drivers/netcx/oid-wdi-task-start-ap) request.

## -enum-fields

### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_START:0xFF000000

The start value of possible IHV-specified reasons.

### -field WDI_CAN_SUSTAIN_AP_REASON_IHV_END:0xFFFFFFFF

The end value of possible IHV-specified reasons.

## -remarks

The **WDI_CAN_SUSTAIN_AP_REASON** enumeration is a value in the [**WDI\_TLV\_INDICATION\_CAN\_SUSTAIN\_AP**](/windows-hardware/drivers/netcx/wdi-tlv-indication-can-sustain-ap) TLV.

## -see-also

[OID_WDI_TASK_START_AP](/windows-hardware/drivers/netcx/oid-wdi-task-start-ap)

[**WDI\_TLV\_INDICATION\_CAN\_SUSTAIN\_AP**](/windows-hardware/drivers/netcx/wdi-tlv-indication-can-sustain-ap)
