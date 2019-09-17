---
UID: NS:dispmprt._DXGKARG_QUERYVIRTUALFUNCTIONLUID
title: _DXGKARG_QUERYVIRTUALFUNCTIONLUID
author: windows-driver-content
description: Arguments used to query virtual function LUID.
tech.root: display
ms.assetid: 0eeb7491-5e3c-47fa-9e81-8a02111672ca
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
f1_keywords:
 - "dispmprt/_DXGKARG_QUERYVIRTUALFUNCTIONLUID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGKARG_QUERYVIRTUALFUNCTIONLUID, DXGKARG_QUERYVIRTUALFUNCTIONLUID, *PDXGKARG_QUERYVIRTUALFUNCTIONLUID, 
req.header: dispmprt.h
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
req.typenames: DXGKARG_QUERYVIRTUALFUNCTIONLUID, *PDXGKARG_QUERYVIRTUALFUNCTIONLUID
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGKARG_QUERYVIRTUALFUNCTIONLUID
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# _DXGKARG_QUERYVIRTUALFUNCTIONLUID structure

## -description

Arguments used to query virtual function LUID.

## -struct-fields

### -field VirtualFunctionIndex

Zero-based offset of the Virtual Function from the first VF exposed by this Physical Function.

### -field pLuid
 
A pointer to a unique LUID that identifies a specific virtual GPU on the host system.

## -remarks

## -see-also
