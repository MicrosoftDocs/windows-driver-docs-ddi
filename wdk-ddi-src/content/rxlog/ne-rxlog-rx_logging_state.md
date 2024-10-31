---
UID: NE:rxlog.RX_LOGGING_STATE
tech.root: ifsk
title: RX_LOGGING_STATE
ms.date: 10/30/2024
targetos: Windows
description: Learn more about the RX_LOGGING_STATE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: rxlog.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - rxlog.h
api_name:
 - RX_LOGGING_STATE
f1_keywords:
 - RX_LOGGING_STATE
 - rxlog/RX_LOGGING_STATE
dev_langs:
 - c++
helpviewer_keywords:
 - RX_LOGGING_STATE
---

## -description

The **RX_LOGGING_STATE** enumeration defines the possible states of the logging system within the RDBSS (Redirected Drive Buffering SubSystem).

## -enum-fields

### -field RX_LOG_UNINITIALIZED

The logging system is uninitialized.

### -field RX_LOG_ENABLED

The logging system is enabled and operational.

### -field RX_LOG_DISABLED

The logging system is initialized but disabled.

### -field RX_LOG_ERROR

There is an error condition within the logging system.
