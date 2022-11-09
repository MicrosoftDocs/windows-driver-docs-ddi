---
UID: NF:acxstreams.AcxStreamGetNotificationId
tech.root: audio
title: AcxStreamGetNotificationId
ms.date: 11/09/2022
targetos: Windows
description: The AcxStreamGetNotificationId function retrieves the Plug and Play notification ID for the specified audio stream.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxstreams.h
api_name:
 - AcxStreamGetNotificationId
f1_keywords:
 - AcxStreamGetNotificationId
 - acxstreams/AcxStreamGetNotificationId
dev_langs:
 - c++
helpviewer_keywords:
 - AcxStreamGetNotificationId
---

## -description

The **AcxStreamGetNotificationId** function retrieves the Plug and Play notification ID for the specified audio stream.

## -parameters

### -param Stream

The ACX stream object for which to retrieve the Plug and Play notification ID.

## -returns

Returns a GUID containing the Plug and Play notification ID for the object specified by the *Stream* parameter.

## -remarks

## -see-also

- [acxstreams.h header](index.md)
