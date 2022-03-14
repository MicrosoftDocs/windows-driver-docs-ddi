---
UID: NC:wdm.GET_DEVICE_RESET_STATUS
tech.root: kernel
title: GET_DEVICE_RESET_STATUS (wdm.h)
ms.date: 03/10/2022
targetos: Windows
description: This topic describes the GET_DEVICE_RESET_STATUS callback function.
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
req.target-min-winverclnt: 
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
 - PGET_DEVICE_RESET_STATUS
f1_keywords:
 - PGET_DEVICE_RESET_STATUS
 - wdm/PGET_DEVICE_RESET_STATUS
dev_langs:
 - c++
helpviewer_keywords:
 - PGET_DEVICE_RESET_STATUS
---

## -description

This topic describes the **GET_DEVICE_RESET_STATUS** callback function.

## -parameters

### -param InterfaceContext [in]

Defines the **PVOID** parameter *InterfaceContext*.

### -param IsResetting [out]

Defines the **PBOOLEAN** parameter *IsResetting*.

### -param ResetTypeSelected [out]

Defines the **PDEVICE_BUS_SPECIFIC_RESET_TYPE** parameter *ResetTypeSelected*.

### -param Flags [out]

Defines the **PDEVICE_RESET_STATUS_FLAGS** parameter *Flags*.

## -returns

NTSTATUS

## -remarks

## -see-also
