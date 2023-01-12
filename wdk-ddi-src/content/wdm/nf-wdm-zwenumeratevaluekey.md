---
UID: NF:wdm.ZwEnumerateValueKey
title: ZwEnumerateValueKey function (wdm.h)
description: The ZwEnumerateValueKey routine gets information about the value entries of an open key.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwEnumerateValueKey function"]
ms.keywords: NtEnumerateValueKey, ZwEnumerateValueKey, ZwEnumerateValueKey routine [Kernel-Mode Driver Architecture], k111_bea1b1ab-2cfe-4d17-abd3-1a45652c70a5.xml, kernel.zwenumeratevaluekey, wdm/NtEnumerateValueKey, wdm/ZwEnumerateValueKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwEnumerateValueKey
 - wdm/ZwEnumerateValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwEnumerateValueKey
---

## -description

The **ZwEnumerateValueKey** routine gets information about the value entries of an open key.

## -parameters

### -param KeyHandle [in]

Handle to the registry key that you want to enumerate value entries for. A successful call to [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey) creates this handle.

### -param Index [in]

The zero-based index of the subkey that you want value information for.

### -param KeyValueInformationClass [in]

Specifies a [KEY_VALUE_INFORMATION_CLASS](/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class) value that determines the type of information returned in the *KeyValueInformation* buffer.

### -param KeyValueInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information.

### -param Length [in]

Specifies the size, in bytes, of the *KeyValueInformation* buffer.

### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the value information. If this routine returns STATUS_SUCCESS, the variable indicates the amount of data returned. If this routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, the variable indicates the buffer size that is required to hold the value information.

## -returns

**ZwEnumerateValueKey** returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:

| Return code | Description |
|---|---|
| **STATUS_BUFFER_OVERFLOW** | The buffer supplied is too small, and only partial data has been written to the buffer. \**ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_BUFFER_TOO_SMALL** | The buffer supplied is too small, and no data has been written to the buffer. \**ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_INVALID_PARAMETER** | The *KeyInformationClass* parameter is not a valid KEY_VALUE_INFORMATION_CLASS value. |
| **STATUS_NO_MORE_ENTRIES** | The *Index* value is out of range for the registry key specified by *KeyHandle*. For example, if a key has *n* subkeys, then for any value greater than *n*-1 the routine returns STATUS_NO_MORE_ENTRIES. |

## -remarks

The *KeyHandle* passed to **ZwEnumerateValueKey** must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the *DesiredAccess* parameter to [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey).

The *Index* is simply a way to select among subkeys with value entries. Two calls to **ZwEnumerateValueKey** with the same *Index* are not guaranteed to return the same results.

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtEnumerateValueKey**" instead of "**ZwEnumerateValueKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**KEY_VALUE_BASIC_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information)

[**KEY_VALUE_FULL_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information)

[**KEY_VALUE_PARTIAL_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)

[ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey)

[ZwQueryValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey)
