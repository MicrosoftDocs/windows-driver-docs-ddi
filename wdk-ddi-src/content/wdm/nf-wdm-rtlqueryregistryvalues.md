---
UID: NF:wdm.RtlQueryRegistryValues
title: RtlQueryRegistryValues function (wdm.h)
description: The RtlQueryRegistryValues routine allows the caller to query several values from the registry subtree with a single call.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["RtlQueryRegistryValues function"]
ms.keywords: RtlQueryRegistryValues, RtlQueryRegistryValues routine [Kernel-Mode Driver Architecture], k109_5a8cb907-8c49-4a88-9494-ff137cf6507d.xml, kernel.rtlqueryregistryvalues, wdm/RtlQueryRegistryValues
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlQueryRegistryValues
 - wdm/RtlQueryRegistryValues
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - RtlQueryRegistryValues
---

## -description

The **RtlQueryRegistryValues** routine allows the caller to query several values from the registry subtree with a single call.

## -parameters

### -param RelativeTo [in]

Specifies whether *Path* is an absolute registry path or is relative to a predefined path as one of the following.

| Value | Meaning |
|---|---|
| RTL_REGISTRY_ABSOLUTE | Path is an absolute registry path. |
| RTL_REGISTRY_CONTROL | Path is relative to **\Registry\Machine\System\CurrentControlSet\Control**. |
| RTL_REGISTRY_DEVICEMAP | Path is relative to **\Registry\Machine\Hardware\DeviceMap**. |
| RTL_REGISTRY_SERVICES | Path is relative to **\Registry\Machine\System\CurrentControlSet\Services**. |
| RTL_REGISTRY_USER | Path is relative to **\Registry\User\CurrentUser**. (For a system process, this is **\User\\.Default**.) |
| RTL_REGISTRY_WINDOWS_NT | Path is relative to **\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion**. |

The *RelativeTo* value can be modified by bitwise-ORing it with one of the following flags.

| Flag | Meaning |
|---|---|
| RTL_REGISTRY_OPTIONAL | Specifies that the key referenced by this parameter and the *Path* parameter are optional. |
| RTL_REGISTRY_HANDLE | Specifies that the *Path* parameter is actually a registry handle to use. |

### -param Path [in]

Pointer to either an absolute registry path or a path relative to the known location specified by the *RelativeTo* parameter. Note that the names of keys in such a path must be known to the caller, including the last key in the path. If the RTL_REGISTRY_HANDLE flag is specified, this parameter is a registry handle for an already opened key to be queried directly.

### -param QueryTable [in, out]

Pointer to a table of one or more value names and subkey names in which the caller is interested. Each table entry contains the address of a caller-supplied [QueryRoutine](./nc-wdm-rtl_query_registry_routine.md) function that will be called for each value name that exists in the registry. The table must be terminated with a **NULL** table entry, which is a table entry with a **NULL** **QueryRoutine** member and a **NULL** **Name** member. The structure for query table entries is defined as follows:

```cpp
typedef struct _RTL_QUERY_REGISTRY_TABLE {
    PRTL_QUERY_REGISTRY_ROUTINE QueryRoutine;
    ULONG Flags;
    PWSTR Name;
    PVOID EntryContext;
    ULONG DefaultType;
    PVOID DefaultData;
    ULONG DefaultLength;
} RTL_QUERY_REGISTRY_TABLE, *PRTL_QUERY_REGISTRY_TABLE;
```

If the caller allocates storage for the query table pointed to by the *QueryTable* parameter, the caller is responsible for releasing this storage after the **RtlQueryRegistryValues** call returns.

#### QueryRoutine

The address of a *QueryRoutine* function that is called with the name, type, data, and data length of a registry value. If this member and the **Name** member are both **NULL**, it marks the end of the table.

A *QueryRoutine* function is declared as follows:

```cpp
NTSTATUS
QueryRoutine (
    IN PWSTR ValueName,
    IN ULONG ValueType,
    IN PVOID ValueData,
    IN ULONG ValueLength,
    IN PVOID Context,
    IN PVOID EntryContext
    );
```

For more information, see [QueryRoutine](./nc-wdm-rtl_query_registry_routine.md).

#### Flags

Flags to control how the remaining members of the **RTL_QUERY_REGISTRY_TABLE** structure are to be interpreted. The following flag bits are defined for this member.

| Value | Meaning |
|---|---|
| RTL_QUERY_REGISTRY_SUBKEY | The **Name** of this table entry is another path to a registry key, and all following table entries are for that key rather than the key specified by the *Path* parameter. This change in focus lasts until the end of the table or until another RTL_REGISTRY_SUBKEY or RTL_QUERY_REGISTRY_TOPKEY entry is seen. Each such entry must specify a path that is relative to the *Path* specified in the call to **RtlQueryRegistryValues**. |
| RTL_QUERY_REGISTRY_TOPKEY | Resets the current registry key handle to the original one specified by the *RelativeTo* and *Path* parameters. This is useful for getting back to the original node after descending into subkeys with the RTL_QUERY_REGISTRY_SUBKEY flag. |
| RTL_QUERY_REGISTRY_REQUIRED | Specifies that this registry value must exist if **DefaultType** = REG_NONE; otherwise, if it is not found, **RtlQueryRegistryValues** immediately exits with a status code of STATUS_OBJECT_NAME_NOT_FOUND. This exit occurs if the **Name** member is **NULL** and the current key has no subkeys, or if **Name** specifies a nonexistent subkey. (If this flag is not specified, then when no match is found for a non-**NULL** **Name**, the routine uses the **DefaultValue** member as the value. When **Name** is **NULL** and the current key has no subkeys, the routine simply skips that table entry.) |
| RTL_QUERY_REGISTRY_NOVALUE | Specifies that even though there is no **Name** for this table entry, all the caller wants is a callback: that is, the caller does not want to enumerate all the values under the current key. *QueryRoutine* is called with **NULL** for *ValueData*, REG_NONE for *ValueType*, and zero for *ValueLength*. |
| RTL_QUERY_REGISTRY_NOEXPAND | For a registry value of type REG_EXPAND_SZ or REG_MULTI_SZ, this flag overrides the default behavior, which is to preprocess the registry value before calling the [QueryRoutine](./nc-wdm-rtl_query_registry_routine.md) routine. By default, **RtlQueryRegistryValues** expands environment variable references in REG_EXPAND_SZ values, and enumerates each null-terminated string in a REG_MULTI_SZ value in a separate *QueryRoutine* call, so that the strings are presented as REG_SZ values that have the same *ValueName*. If this flag is set, *QueryRoutine* receives the raw REG_EXPAND_SZ or REG_MULTI_SZ value from the registry. For more information about the data formats for these values, see [KEY_VALUE_BASIC_INFORMATION](./ns-wdm-_key_value_basic_information.md). |
| RTL_QUERY_REGISTRY_DIRECT | The **QueryRoutine** member is not used (and must be **NULL**), and the *EntryContext* points to the buffer to store the value. If the caller sets this flag, the caller should additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag to guard against buffer overflow. For more information, see the Remarks section. |
| RTL_QUERY_REGISTRY_TYPECHECK | Use this flag with the RTL_QUERY_REGISTRY_DIRECT flag to verify that the REG\_*XXX* type of the stored registry value matches the type expected by the caller. If the types do not match, the call fails. For more information, see the Remarks section. |
| RTL_QUERY_REGISTRY_DELETE | This flag is used to delete value keys after they have been queried. |

Starting with Windows 2000, inbox support is provided for all flag bits in the preceding table, with the exception of RTL_QUERY_REGISTRY_TYPECHECK. Inbox support for RTL_QUERY_REGISTRY_TYPECHECK is available starting with Windows 8. For earlier versions of Windows, support for RTL_QUERY_REGISTRY_TYPECHECK is provided through Windows Update. For more information, see Remarks.

#### Name

This is the name of a Value that the caller queried. If **Name** is **NULL**, the *QueryRoutine* function specified for this table entry is called for all values associated with the current registry key. If the RTL_QUERY_REGISTRY_DIRECT flag is set, a non-**NULL** value for **Name** must be provided.

#### EntryContext

If the RTL_QUERY_REGISTRY_DIRECT flag is set, this is a pointer to the buffer to store the result of the query operation for this key. Otherwise, this value is passed as the *EntryContext* parameter of *QueryRoutine*.

#### DefaultType

The least significant byte of this member specifies the REG_*XXX* type of the data to be returned, if no matching key is found and the RTL_QUERY_REGISTRY_REQUIRED flag is not specified. Specify REG_NONE for no default type. If the RTL_QUERY_REGISTRY_TYPECHECK flag is set, the most significant byte of this member specifies the REG_*XXX* type of the stored registry value that the caller expects. Bits 8 to 23 of this member are reserved and should be zero.

#### DefaultData

A pointer to the default value to be returned if no matching key is found and the RTL_QUERY_REGISTRY_REQUIRED flag is not specified. This member is ignored if **DefaultType** = REG_NONE. Otherwise, the type of data pointed to by **DefaultData** should conform to the registry value type specified by the **DefaultType** member. For more information registry value types, see the definition of the *Type* parameter in [KEY_VALUE_BASIC_INFORMATION](./ns-wdm-_key_value_basic_information.md).

#### DefaultLength

Specifies the length, in bytes, of the **DefaultData** member. If **DefaultType** is REG_SZ, REG_EXPAND_SZ, or REG_MULTI_SZ, callers can optionally specify zero to indicate **RtlQueryRegistryValues** should compute the length based on the default data value. If **DefaultType** = REG_NONE, this member is ignored.

### -param Context [in, optional]

Specifies the value passed as the *Context* parameter of a *QueryRoutine* function each time it is called.

### -param Environment [in, optional]

Pointer to the environment used when expanding variable values in REG_EXPAND_SZ registry values, or a **NULL** pointer (optional).

## -returns

**RtlQueryRegistryValues** returns an NTSTATUS code. The possible return values include:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The entire query table was processed successfully. |
| **STATUS_INVALID_PARAMETER** | Processing of the query table terminated with an invalid table entry. A table entry can be invalid if the specified flags require the **QueryRoutine** or **Name** member to be non-**NULL**, but a **NULL** value was provided. |
| **STATUS_OBJECT_NAME_NOT_FOUND** | The *Path* parameter does not match a valid key, or processing of the query table terminated with an entry with the RTL_QUERY_REGISTRY_REQUIRED flag set and no matching key is found. This occurs if the **Name** member is **NULL** and the current key has no subkeys, or if **Name** specifies a nonexistent subkey. |
| **STATUS_BUFFER_TOO_SMALL** | The RTL_QUERY_REGISTRY_DIRECT flag is set, and the buffer specified by **EntryContext** is too small to hold the key value data. |
| **STATUS_OBJECT_TYPE_MISMATCH** | The RTL_QUERY_REGISTRY_TYPECHECK flag is set and the type of the stored registry value does not match the type expected by the caller. |

**RtlQueryRegistryValues** also terminates processing of the table if the *QueryRoutine* function for a table entry returns an NTSTATUS error code, and returns that error code as its result. (With one exception: If *QueryRoutine* returns STATUS_BUFFER_TOO_SMALL, the error code is ignored.)

## -remarks

The caller specifies an initial key path and a table. The table contains one or more entries that describe the key values and subkey names in which the caller is interested. The table is terminated by an entry with a **NULL** **QueryRoutine** member and a **NULL** **Name** member. The table must be allocated from nonpaged pool.

Kernel-mode drivers must specify the RTL_QUERY_REGISTRY_NOEXPAND flag to prevent calling environment variable routines. These routines are unsafe, so kernel-mode drivers should not use them.

> [!CAUTION]
> If you use the RTL_QUERY_REGISTRY_DIRECT flag, an untrusted user-mode application may be able to cause a buffer overflow. A buffer overflow can occur if a driver uses this flag to read a registry value to which the wrong type is assigned. In all cases, a driver that uses the RTL_QUERY_REGISTRY_DIRECT flag should additionally use the RTL_QUERY_REGISTRY_TYPECHECK flag to prevent such overflows.

If the RTL_QUERY_REGISTRY_TYPECHECK flag is set in a table entry, the caller must specify the expected REG_*XXX* type in the 8 most significant bits (MSBs) of the 32-bit **DefaultType** member of the table entry. As shown in the following code example, the RTL_QUERY_REGISTRY_TYPECHECK_SHIFT constant, which is defined to be 24, can be used as the shift count required to place the expected REG_*XXX* type in the 8 MSBs of the **DefaultType** member.

```cpp
RTL_QUERY_REGISTRY_TABLE QueryRegTable[2];    
...
QueryRegTable[0].DefaultType = (REG_SZ << RTL_QUERY_REGISTRY_TYPECHECK_SHIFT) | REG_NONE;
...
QueryRegTable[1].DefaultType = (REG_DWORD << RTL_QUERY_REGISTRY_TYPECHECK_SHIFT) | REG_NONE;
...
```

Starting with Windows 8, if an **RtlQueryRegistryValues** call accesses an untrusted hive, and the caller sets the RTL_QUERY_REGISTRY_DIRECT flag for this call, the caller must additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag. A violation of this rule by a call from user mode causes an exception.  A violation of this rule by a call from kernel mode causes a 0x139 bug check (KERNEL_SECURITY_CHECK_FAILURE).

Only system hives are trusted. An **RtlQueryRegistryValues** call that accesses a system hive does not cause an exception or a bug check if the RTL_QUERY_REGISTRY_DIRECT flag is set and the RTL_QUERY_REGISTRY_TYPECHECK flag is not set. However, as a best practice, the RTL_QUERY_REGISTRY_TYPECHECK flag should always be set if the RTL_QUERY_REGISTRY_DIRECT flag is set.

Similarly, in versions of Windows before Windows 8, as a best practice, an **RtlQueryRegistryValues** call that sets the RTL_QUERY_REGISTRY_DIRECT flag should additionally set the RTL_QUERY_REGISTRY_TYPECHECK flag. However, failure to follow this recommendation does not cause an exception or a bug check.

The following is a list of system hives:

- \REGISTRY\MACHINE\HARDWARE

- \REGISTRY\MACHINE\SOFTWARE

- \REGISTRY\MACHINE\SYSTEM

- \REGISTRY\MACHINE\SECURITY

- \REGISTRY\MACHINE\SAM

Support for the RTL_QUERY_REGISTRY_TYPECHECK flag is available through Windows Update for Windows 7, Windows Vista, Windows Server 2003, and Windows XP. For more information about this update, see [Vulnerabilities in Windows Kernel Could Allow Elevation of Privilege (2393802)](https://go.microsoft.com/fwlink/p/?linkid=210698). In versions of these operating systems that do not have this update, the caller can use the RTL_QUERY_REGISTRY_TYPECHECK flag. However, this flag is ignored by the **RtlQueryRegistryValues** routine.

Starting with Windows Driver Kit (WDK) 8, the RTL_QUERY_REGISTRY_TYPECHECK flag is defined in the Wdm.h header file as follows:

```cpp
#define RTL_QUERY_REGISTRY_TYPECHECK 0x00000100
```

If an entry does not specify the RTL_QUERY_REGISTRY_DIRECT flag, **RtlQueryRegistryValues** uses the specified *QueryRoutine* function to report the value name, type, data, and data length, in bytes, to the caller. If the **Name** member of the entry is **NULL**, **RtlQueryRegistryValues** reports every direct subkey of the key. If the key type is REG_MULTI_SZ and the RTL_QUERY_REGISTRY_NOEXPAND flag not is specified, the routine calls *QueryRoutine* separately for each individual string; otherwise the routine reports it as a single value. If an entry specifies the RTL_QUERY_REGISTRY_DIRECT flag, **RtlQueryRegistryValues** stores the value of the key in the buffer pointed to by the entry's **EntryContext** member. The format of the returned data is as follows.

| Key data type | How data is returned |
|---|---|
| A null-terminated Unicode string (such as REG_SZ, REG_EXPAND_SZ). | **EntryContext** must point to an initialized [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure. If the **Buffer** member of **UNICODE_STRING** is **NULL**, the routine allocates storage for the string data. Otherwise, it stores the string data in the buffer that **Buffer** points to. |
| REG_MULTI_SZ | You must specify the RTL_QUERY_REGISTRY_NOEXPAND flag for this key data type. **EntryContext** points to an initialized **UNICODE_STRING** structure. The routine stores the key value as a single string value. Each individual component within the string is terminated by a zero. If the **Buffer** member of **UNICODE_STRING** is **NULL**, the routine allocates storage for the string data. Otherwise, it stores the string data in the buffer that **Buffer** points to. |
| Nonstring data with size, in bytes, \<= **sizeof**(ULONG) | The value is stored in the memory location specified by **EntryContext**. |
| Nonstring data with size, in bytes, \> **sizeof**(ULONG) | The buffer pointed to by **EntryContext** must begin with a signed LONG value. The magnitude of the value must specify the size, in bytes, of the buffer. If the sign of the value is negative, **RtlQueryRegistryValues** will only store the data of the key value. Otherwise, it will use the first ULONG in the buffer to record the value length, in bytes, the second ULONG to record the value type, and the rest of the buffer to store the value data. |

If an error occurs at any stage of processing of the query table, **RtlQueryRegistryValues** stops processing the table and returns the error status.

See [ZwSetValueKey](./nf-wdm-zwsetvaluekey.md) for a description of the possible REG_*XXX* values.

## -see-also

[QueryRoutine](./nc-wdm-rtl_query_registry_routine.md)

[RtlZeroMemory](./nf-wdm-rtlzeromemory.md)

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[ZwEnumerateKey](./nf-wdm-zwenumeratekey.md)

[ZwEnumerateValueKey](./nf-wdm-zwenumeratevaluekey.md)

[ZwSetValueKey](./nf-wdm-zwsetvaluekey.md)