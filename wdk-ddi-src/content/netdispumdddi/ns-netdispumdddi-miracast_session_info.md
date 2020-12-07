---
UID: NS:netdispumdddi.__unnamed_union_5
title: MIRACAST_SESSION_INFO (netdispumdddi.h)
description: Contains info on a wireless display (Miracast) connected session.
old-location: display\miracast_session_info.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["MIRACAST_SESSION_INFO structure"]
ms.keywords: MIRACAST_SESSION_INFO, MIRACAST_SESSION_INFO union [Display Devices], display.miracast_session_info, netdispumdddi/MIRACAST_SESSION_INFO
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: MIRACAST_SESSION_INFO
f1_keywords:
 - MIRACAST_SESSION_INFO
 - netdispumdddi/MIRACAST_SESSION_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Netdispumdddi.h
api_name:
 - MIRACAST_SESSION_INFO
---

# MIRACAST_SESSION_INFO structure


## -description

Contains info on a wireless display (Miracast) connected session.

## -struct-fields

### -field MonitorConnected

If set, the monitor (the source) is connected to a Miracast sink.

### -field ReducedModeListDueToBandwidth

If set, the user-mode driver has reduced the modes exposed to the operating system based on the current suggested encode rate.

### -field Reserved

Reserved for system use and should be set to zero.

### -field Value

Holds a 32-bit value that identifies the Miracast connected session.

