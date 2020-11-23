---
UID: NF:sensorsdriversutils.GetMethodArgumentFromAcpi
title: GetMethodArgumentFromAcpi function (sensorsdriversutils.h)
description: The GetMethodArgumentFromAcpi function reads the requested ACPI entry using the supplied method name.
tech.root: sensors
ms.assetid: 62776cea-ef29-48be-ae0d-ad460c7f910c
ms.date: 04/19/2018
keywords: ["GetMethodArgumentFromAcpi function"]
ms.keywords: GetMethodArgumentFromAcpi
req.header: sensorsdriversutils.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - GetMethodArgumentFromAcpi
 - sensorsdriversutils/GetMethodArgumentFromAcpi
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - GetMethodArgumentFromAcpi
product:
 - Windows
---

# GetMethodArgumentFromAcpi function


## -description

The GetMethodArgumentFromAcpi function reads the requested ACPI entry by using the supplied method name.

## -parameters

### -param Device

Supplies the WDF device object.

### -param MethodName

Supplies the method name to read.

### -param MethodNameLength

Supplies the method name length in bytes.

### -param MethodArgument

Supplies the address at which to write the method argument.

### -param MethodArgumentLength

Supplies the length in bytes of the buffer in which to save the MethodArgument.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

