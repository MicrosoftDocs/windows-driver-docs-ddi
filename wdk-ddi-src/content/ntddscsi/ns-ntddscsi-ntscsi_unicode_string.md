---
UID: NS:ntddscsi._NTSCSI_UNICODE_STRING
title: NTSCSI_UNICODE_STRING
description: Storage port drivers can use the NTSCSI_UNICODE_STRING structure to define Unicode strings.
tech.root: storage
ms.date: 05/20/2022
keywords: ["NTSCSI_UNICODE_STRING structure"]
ms.keywords: NTSCSI_UNICODE_STRING, NTSCSI_UNICODE_STRING, *PNTSCSI_UNICODE_STRING
req.header: ntddscsi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NTSCSI_UNICODE_STRING
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _NTSCSI_UNICODE_STRING
 - ntddscsi/_NTSCSI_UNICODE_STRING
 - NTSCSI_UNICODE_STRING
 - ntddscsi/NTSCSI_UNICODE_STRING
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddscsi.h
api_name:
 - _NTSCSI_UNICODE_STRING
 - NTSCSI_UNICODE_STRING
product:
 - Windows
---

# NTSCSI_UNICODE_STRING structure

## -description

Storage port drivers can use the **NTSCSI_UNICODE_STRING** structure to define Unicode strings.

## -struct-fields

### -field Length

Length, in bytes, of the string stored in **Buffer**.

### -field MaximumLength

Total length, in bytes, of memory allocated for **Buffer**.

### -field Buffer

Pointer to a buffer used to contain a string of wide characters.

## -remarks

If the string is null-terminated, **Length** does not include the trailing null character.

**MaximumLength** is used to indicate the length of **Buffer** so that if the string is passed to a conversion routine, the returned string does not exceed the buffer size.

## -see-also

[UNICODE_STRING](/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_unicode_string)
