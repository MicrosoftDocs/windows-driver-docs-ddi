---
UID: NE:storport._STOR_EVENT_TYPE
title: STOR_EVENT_TYPE
author: windows-driver-content
description: The STOR_EVENT_TYPE enum identifies the type of event object initialized by a miniport.
tech.root: storage
ms.assetid: f9733b74-5773-4d29-b488-656064403e6a
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: enum
ms.keywords: STOR_EVENT_TYPE, STOR_EVENT_TYPE, *PSTOR_EVENT_TYPE, 
req.header: storport.h
f1_keywords:
 - "storport/STOR_EVENT_TYPE"
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: STOR_EVENT_TYPE, *PSTOR_EVENT_TYPE
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - storport.h
api_name: 
 - STOR_EVENT_TYPE
product: 
 - Windows
targetos: Windows
---

# STOR_EVENT_TYPE enumeration

## -description

The **STOR_EVENT_TYPE** enum identifies the type of event object initialized by a miniport.

## -enum-fields

### -field StorNotificationEvent

The event is a notification event.

### -field StorSynchronizationEvent

The event is a synchronization event.

## -remarks

A miniport initializes an event object by calling [**StorPortInitializeEvent**](nf-storport-storport_initialize_event.md), passing in a **STOR_EVENT_TYPE** enum to identify the type of the event object.

## -see-also

[**StorPortInitializeEvent**](nf-storport-storport_initialize_event.md)
