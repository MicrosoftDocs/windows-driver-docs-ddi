---
UID: NC:wdm.DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER
tech.root: kernel
title: DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER (wdm.h)
ms.date: 03/11/2022
targetos: Windows
description: This topic describes the DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER
f1_keywords:
 - DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER
 - wdm/DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER
dev_langs:
 - c++
helpviewer_keywords:
 - DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER
---

## -description

This topic describes the **DEVICE_QUERY_BUS_SPECIFIC_RESET_HANDLER** callback function.

## -parameters

### -param InterfaceContext [in]

Defines the **PVOID** parameter *InterfaceContext*.

### -param ResetInfoCount [out]

Defines the **PULONG** parameter *ResetInfoCount*.

### -param ResetInfoSupported [out]

Defines the **PDEVICE_BUS_SPECIFIC_RESET_INFO** parameter *ResetInfoCount*.

## -returns

NTSTATUS

## -remarks

## -see-also
