---
UID: NS:dot11wificxintf._WDI_MESSAGE_HEADER
tech.root: netvista
title: WDI_MESSAGE_HEADER (dot11wificxintf.h)
ms.date: 10/02/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_MESSAGE_HEADER structure defines the WiFi message header. All WiFi command messages must start with this header.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxintf.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxintf.h
api_name:
 - _WDI_MESSAGE_HEADER
 - PWDI_MESSAGE_HEADER
 - WDI_MESSAGE_HEADER
f1_keywords:
 - _WDI_MESSAGE_HEADER
 - dot11wificxintf/_WDI_MESSAGE_HEADER
 - PWDI_MESSAGE_HEADER
 - dot11wificxintf/PWDI_MESSAGE_HEADER
 - WDI_MESSAGE_HEADER
 - dot11wificxintf/WDI_MESSAGE_HEADER
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is now in maintenance mode and will only receive high priority fixes. 

> [!NOTE]
For the WDI version of this structure, see [**WDI_MESSAGE_HEADER**](../dot11wdi/ns-dot11wdi-_wdi_message_header.md).

The WDI_MESSAGE_HEADER structure defines the WiFi message header. All WiFi command messages must start with this header.

## -struct-fields

### -field PortId

Specifies the identifier for the Port object that this command is targeted for. For commands on the Adapter object, this is 0xFFFF.

### -field Reserved

This member is reserved.

### -field Status

Specifies the operation completion status for output messages. For input messages, this field is reserved.

### -field TransactionId

Specifies the transaction ID. This value is used to match host-sent messages with function responses.  This value must be unique among all outstanding transactions.  For notifications, the TransactionId must be set to 0 by the function.

### -field IhvSpecificId

Specifies an IHV-specific ID for this message. This can be used by IHVs for debugging purpose.

## -see-also

[Introduction to the Wi-Fi WDF class extension (WiFiCx)](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx)

[WiFiCx message structure](/windows-hardware/drivers/netcx/wificx-message-structure)

