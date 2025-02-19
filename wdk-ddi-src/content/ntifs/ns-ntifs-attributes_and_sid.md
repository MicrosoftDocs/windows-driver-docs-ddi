---
UID: NS:ntifs._ATTRIBUTES_AND_SID
tech.root: ifsk
title: ATTRIBUTES_AND_SID
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the ATTRIBUTES_AND_SID structure.
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
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: ATTRIBUTES_AND_SID, *PATTRIBUTES_AND_SID
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
 - _ATTRIBUTES_AND_SID
 - PATTRIBUTES_AND_SID
 - ATTRIBUTES_AND_SID
f1_keywords:
 - _ATTRIBUTES_AND_SID
 - ntifs/_ATTRIBUTES_AND_SID
 - PATTRIBUTES_AND_SID
 - ntifs/PATTRIBUTES_AND_SID
 - ATTRIBUTES_AND_SID
 - ntifs/ATTRIBUTES_AND_SID
dev_langs:
 - c++
helpviewer_keywords:
 - _ATTRIBUTES_AND_SID
---

## -description

The **ATTRIBUTES_AND_SID** structure associates a set of attributes with a security identifier (SID).

## -struct-fields

### -field Attributes

Value that represents the attributes associated with the SID.

### -field SidStart

Starting point of the SID.
