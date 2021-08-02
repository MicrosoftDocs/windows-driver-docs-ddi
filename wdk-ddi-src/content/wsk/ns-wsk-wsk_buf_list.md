---
UID: NS:wsk._WSK_BUF_LIST
tech.root: netvista
title: WSK_BUF_LIST
ms.date: 08/02/2021
targetos: Windows
description: The WSK_BUF_LIST structure is used to send multiple datagrams via a single call to WskSendMessages.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wsk.h
req.include-header: wsk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: WSK_BUF_LIST, *PWSK_BUF_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wsk.h
api_name:
 - _WSK_BUF_LIST
 - PWSK_BUF_LIST
 - WSK_BUF_LIST
f1_keywords:
 - _WSK_BUF_LIST
 - wsk/_WSK_BUF_LIST
 - PWSK_BUF_LIST
 - wsk/PWSK_BUF_LIST
 - WSK_BUF_LIST
 - wsk/WSK_BUF_LIST
dev_langs:
 - c++
---

## -description

The **WSK_BUF_LIST** structure is used to send multiple datagrams via a single call to [**WskSendMessages**](nc-wsk-pfn_wsk_send_messages.md).

## -struct-fields

### -field Next

A pointer to a **WSK_BUF_LIST** structure containing the next data buffer in the list.

### -field Buffer

An initialized [**WSK_BUF**](ns-wsk-_wsk_buf.md) structure that describes a data buffer.

## -remarks

## -see-also

[**WskSendMessages**](nc-wsk-pfn_wsk_send_messages.md)

[**WSK_BUF**](ns-wsk-_wsk_buf.md)

