---
UID: NS:ksmedia._tagKSJACK_DESCRIPTION3
tech.root: stream
title: KSJACK_DESCRIPTION3 (ksmedia.h)
ms.date: 03/08/2022
targetos: Windows
description: This topic describes the KSJACK_DESCRIPTION3 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: KSJACK_DESCRIPTION3, *PKSJACK_DESCRIPTION3
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - _tagKSJACK_DESCRIPTION3
 - PKSJACK_DESCRIPTION3
 - KSJACK_DESCRIPTION3
f1_keywords:
 - _tagKSJACK_DESCRIPTION3
 - ksmedia/_tagKSJACK_DESCRIPTION3
 - PKSJACK_DESCRIPTION3
 - ksmedia/PKSJACK_DESCRIPTION3
 - KSJACK_DESCRIPTION3
 - ksmedia/KSJACK_DESCRIPTION3
dev_langs:
 - c++
helpviewer_keywords:
 - _tagKSJACK_DESCRIPTION3
---

## -description

This topic describes the **KSJACK_DESCRIPTION3** structure.

## -struct-fields

### -field ConfigId

Defines the **ULONG** member **ConfigId**.

## -remarks

This is a driver defined bitmask or enum describing the current configuration. Changing this value causes audioendpointbuilder to refresh the cache to ensure that the published endpoint matches the current config.

## -see-also
