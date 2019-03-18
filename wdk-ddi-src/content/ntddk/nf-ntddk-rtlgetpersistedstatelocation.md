---
UID: NF:ntddk.RtlGetPersistedStateLocation
title: RtlGetPersistedStateLocation function (ntddk.h)
description: Retrieves the redirected location for the specified SourceID from the redirection map.
ms.assetid: 028aab59-4047-484e-a06b-5ef03b5d0cdb
ms.date: 10/19/2018
ms.topic: function
ms.keywords: RtlGetPersistedStateLocation
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- RtlGetPersistedStateLocation
product:
- Windows
targetos: Windows

---

# RtlGetPersistedStateLocation function


## -description

Retrieves the redirected location for the specified SourceID from the redirection map.

## -parameters

### -param SourceID
[_In_] The identifier to lookup in the redirection map.

### -param CustomValue
[_In_opt_] Optional. The value to retrieve, if it's different than the default value.

### -param DefaultPath
[_In_opt_] Optional. If an entry for the **SourceID** value cannot be found in the map, returns this value.

### -param StateLocationType
[_In_] A [**STATE_LOCATION_TYPE**](ne-ntddk-_state_location_type.md)-type value that indicates the type of State to look up; registry or file system.

### -param TargetPath
[_In_] A pointer to a Unicode string that receives the value. If the call is successful. The string is null-terminated.

### -param BufferLengthIn
[_In_] The size of the string pointed to by _TargetPath_, in bytes.

### -param BufferLengthOut
[_Out_opt_] Optional. If specified, returns the number of bytes written to the buffer in case the call is successful; number of bytes required if the call fails with the STATUS_BUFFER_OVERFLOW error code.

## -returns
Returns an NTSTATUS value that indicates the success of failure of the operation. Otherwise returns an appropriate [NTSTATUS value](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -see-also
[**STATE_LOCATION_TYPE**](ne-ntddk-_state_location_type.md)
