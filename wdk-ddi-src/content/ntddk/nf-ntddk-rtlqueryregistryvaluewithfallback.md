---
UID: NF:ntddk.RtlQueryRegistryValueWithFallback
title: RtlQueryRegistryValueWithFallback function
author: windows-driver-content
description: Retrieves a value entry for a registry key by using, a primary handle; if not found, uses the fallback handle.
tech.root: kernel
ms.assetid: 5da678a5-2619-423d-9749-522a235b3da4
ms.author: windowsdriverdev
ms.date: 9/30/2018
ms.topic: function
ms.keywords: RtlQueryRegistryValueWithFallback
req.header: ntddk.h
req.include-header: wdm.h
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	DllExport
api_location: 
-	NtosKrnl.exe
api_name: 
-	RtlQueryRegistryValueWithFallback
product: Windows
targetos: Windows


---

# RtlQueryRegistryValueWithFallback function


## -description

Retrieves a value entry for a registry key by using, a primary handle; if not found, uses the fallback handle.

## -parameters

### -param PrimaryHandle
[in] The handle to the key that is first used to query the value entries. This handle is created by a successful call to [**ZwCreateKey**](../wdm/nf-wdm-zwcreatekey.md) or [**ZwOpenKey**](../wdm/nf-wdm-zwopenkey.md).

### -param FallbackHandle
[in] The handle to use for querying the key if value is not found using the handle specified by _PrimaryHandle_.

### -param ValueName
[in] A pointer to string that contains the name of the value for which to retrieve data.

### -param ValueLength
[in] Specifies the size, in bytes, of the _ValueName_ string.

### -param ValueType
[Out] A pointer to a ULONG variable that receives the the type of the value being queried.

### -param ValueData
[out] A pointer to a buffer that receives the value data.

### -param ResultLength
[out] A pointer to a variable that receives the value data size, in bytes. If the return value is STATUS_SUCCESS, indicates the number of bytes written to the _ValueData_ buffer. If the call returns STATUS_BUFFER_OVERFLOW, indicates the number of bytes required. Callers can use that value to determine the size of _ValueData_ buffer required to hold the data information.

## -returns
Returns STATUS_SUCCESS on success, or the appropriate error code on failure.

## -remarks

## -see-also
[Using the Registry in a Driver](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-the-registry-in-a-driver)