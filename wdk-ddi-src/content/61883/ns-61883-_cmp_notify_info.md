---
UID: NS:61883._CMP_NOTIFY_INFO
title: _CMP_NOTIFY_INFO (61883.h)
description: This structure is used by the PCMP_NOTIFY_ROUTINE callback.
old-location: ieee\cmp_notify_info.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["CMP_NOTIFY_INFO structure"]
ms.keywords: "*PCMP_NOTIFY_INFO, 61883/CMP_NOTIFY_INFO, 61883/PCMP_NOTIFY_INFO, CMP_NOTIFY_INFO, CMP_NOTIFY_INFO structure [Buses], IEEE.cmp_notify_info, PCMP_NOTIFY_INFO, PCMP_NOTIFY_INFO structure pointer [Buses], _CMP_NOTIFY_INFO"
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: CMP_NOTIFY_INFO, *PCMP_NOTIFY_INFO
f1_keywords:
 - _CMP_NOTIFY_INFO
 - 61883/_CMP_NOTIFY_INFO
 - PCMP_NOTIFY_INFO
 - 61883/PCMP_NOTIFY_INFO
 - CMP_NOTIFY_INFO
 - 61883/CMP_NOTIFY_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 61883.h
api_name:
 - _CMP_NOTIFY_INFO
 - PCMP_NOTIFY_INFO
 - CMP_NOTIFY_INFO
---

# _CMP_NOTIFY_INFO structure


## -description

This structure is used by the <a href="/windows-hardware/drivers/ddi/61883/nc-61883-pcmp_notify_routine">PCMP_NOTIFY_ROUTINE</a> callback.

## -struct-fields

### -field hPlug

The handle of a plug for the notification.

### -field Pcr

A plug control register.

### -field Context

A context.

## -see-also

<a href="/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>

