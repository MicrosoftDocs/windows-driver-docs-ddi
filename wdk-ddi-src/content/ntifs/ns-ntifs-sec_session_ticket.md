---
UID: NS:ntifs._SEC_SESSION_TICKET
tech.root: ifsk
title: SEC_SESSION_TICKET
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SEC_SESSION_TICKET structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SEC_SESSION_TICKET, *PSEC_SESSION_TICKET
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SEC_SESSION_TICKET
 - PSEC_SESSION_TICKET
 - SEC_SESSION_TICKET
f1_keywords:
 - _SEC_SESSION_TICKET
 - ntifs/_SEC_SESSION_TICKET
 - PSEC_SESSION_TICKET
 - ntifs/PSEC_SESSION_TICKET
 - SEC_SESSION_TICKET
 - ntifs/SEC_SESSION_TICKET
dev_langs:
 - c++
helpviewer_keywords:
 - _SEC_SESSION_TICKET
---

## -description

The **SEC_SESSION_TICKET** structure is used to represent a session ticket in secure communication protocols. It contains information about the session ticket size and the actual ticket data.

The SessionTicketSize must accurately reflect the number of bytes used in the SessionTicket array to ensure correct processing and interpretation of the ticket data.
This structure is typically used in scenarios where maintaining session continuity is important, such as in high-performance applications or environments with frequent secure connections.
Proper management of session tickets can enhance both security and performance by minimizing the need for repeated handshakes and reducing latency in secure communications.

## -struct-fields

### -field SessionTicketSize

The size, in bytes, of the session ticket contained in the **SessionTicket** array. This size indicates how much data is stored in the session ticket.

### -field SessionTicket[ANYSIZE_ARRAY]

Array of bytes representing the session ticket. This ticket is used in TLS 1.3 and later versions to resume secure sessions. The array is flexible in size, allowing it to accommodate varying amounts of ticket data.
