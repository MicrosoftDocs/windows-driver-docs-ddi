---
UID: NE:dot11wificxintf._WDI_OPERATION_MODE
tech.root: netvista
title: WDI_OPERATION_MODE (dot11wificxintf.h)
ms.date: 07/09/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_OPERATION_MODE enum defines operation modes.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxintf.h
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
 - dot11wificxintf.h
api_name:
 - _WDI_OPERATION_MODE
 - WDI_OPERATION_MODE
f1_keywords:
 - _WDI_OPERATION_MODE
 - dot11wificxintf/_WDI_OPERATION_MODE
 - WDI_OPERATION_MODE
 - dot11wificxintf/WDI_OPERATION_MODE
dev_langs:
 - c++
---

## -description

The WDI_OPERATION_MODE enumeration defines operation modes.

## -enum-fields

### -field WDI_OPERATION_MODE_STA

Infrastructure client.

### -field WDI_OPERATION_MODE_P2P_DEVICE

Wi-Fi Direct Device.

### -field WDI_OPERATION_MODE_P2P_CLIENT

Wi-Fi Direct Client.

### -field WDI_OPERATION_MODE_P2P_GO

Wi-Fi Direct Group Owner.

## -remarks

The **WDI_OPERATION_MODE** enum is used in the payload buffer of the [**WDI_TLV_OPERATION_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-operation-mode) TLV.

## -see-also

[**WDI_TLV_OPERATION_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-operation-mode) 