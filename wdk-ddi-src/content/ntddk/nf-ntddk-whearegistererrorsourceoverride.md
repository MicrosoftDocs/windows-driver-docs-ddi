---
UID: NF:ntddk.WheaRegisterErrorSourceOverride
tech.root: kernel
title: WheaRegisterErrorSourceOverride (ntddk.h)
ms.date: 03/25/2022
targetos: Windows
description: This topic describes the WheaRegisterErrorSourceOverride function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: Ntddk.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
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
 - ntddk.h
api_name:
 - WheaRegisterErrorSourceOverride
f1_keywords:
 - WheaRegisterErrorSourceOverride
 - ntddk/WheaRegisterErrorSourceOverride
dev_langs:
 - c++
helpviewer_keywords:
 - WheaRegisterErrorSourceOverride
---

## -description

This topic describes the **WheaRegisterErrorSourceOverride** function.

## -parameters

### -param OverrideSettings [in]

Defines the **WHEA_ERROR_SOURCE_OVERRIDE_SETTINGS** parameter *OverrideSettings*.

### -param OverrideConfig [in]

Defines the **PWHEA_ERROR_SOURCE_CONFIGURATION** parameter *OverrideConfig*.

### -param OverrideCallback [in]

Defines the **WHEA_SIGNAL_HANDLER_OVERRIDE_CALLBACK** parameter *OverrideCallback*.

## -returns

NTSTATUS

## -remarks

## -see-also
