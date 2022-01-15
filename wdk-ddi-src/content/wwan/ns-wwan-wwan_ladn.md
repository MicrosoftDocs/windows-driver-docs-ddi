---
UID: NS:wwan._WWAN_LADN
tech.root: netvista
title: WWAN_LADN
ms.date: wwan_ladn
targetos: Windows
description: The WWAN_LADN structure represents a Local Area Data Network (LADN).
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_LADN, *PWWAN_LADN
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_LADN
 - PWWAN_LADN
 - WWAN_LADN
f1_keywords:
 - _WWAN_LADN
 - wwan/_WWAN_LADN
 - PWWAN_LADN
 - wwan/PWWAN_LADN
 - WWAN_LADN
 - wwan/WWAN_LADN
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_LADN
---

## -description

The **WWAN_LADN** structure represents a Local Area Data Network (LADN).

## -struct-fields

### -field AccessString

The selected APN/DNN for an established context/session.

### -field TaiList

A [**WWAN_TAI_LIST**](ns-wwan-wwan_tai_list.md) structure that represents a tracking area identity (TAI) list.

## -remarks

## -see-also

[**WWAN_TAI_LIST**](ns-wwan-wwan_tai_list.md)

[**WWAN_LADN_LIST**](ns-wwan-wwan_ladn_list.md)