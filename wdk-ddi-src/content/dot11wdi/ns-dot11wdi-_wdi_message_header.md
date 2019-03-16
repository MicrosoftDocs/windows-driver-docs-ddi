---
UID: NS:dot11wdi._WDI_MESSAGE_HEADER
title: _WDI_MESSAGE_HEADER (dot11wdi.h)
description: The WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI command messages must start with this header.
old-location: netvista\wdi_message_header.htm
tech.root: netvista
ms.assetid: 69c3ebf5-8805-47d0-a507-d2e3e1d1b0df
ms.date: 05/02/2018
ms.keywords: "*PWDI_MESSAGE_HEADER, PWDI_MESSAGE_HEADER, PWDI_MESSAGE_HEADER structure pointer [Network Drivers Starting with Windows Vista], WDI_MESSAGE_HEADER, WDI_MESSAGE_HEADER structure [Network Drivers Starting with Windows Vista], _WDI_MESSAGE_HEADER, dot11wdi/PWDI_MESSAGE_HEADER, dot11wdi/WDI_MESSAGE_HEADER, netvista.wdi_message_header"
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- dot11wdi.h
api_name:
- WDI_MESSAGE_HEADER
product:
- Windows
targetos: Windows
req.typenames: WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER
---

# _WDI_MESSAGE_HEADER structure


## -description


The 
  WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI  command messages must start with this header.


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

