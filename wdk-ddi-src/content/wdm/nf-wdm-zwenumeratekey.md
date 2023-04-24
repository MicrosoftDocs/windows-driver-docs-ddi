---
UID: NF:wdm.ZwEnumerateKey
title: ZwEnumerateKey function (wdm.h)
description: The ZwEnumerateKey routine returns information about a subkey of an open registry key.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwEnumerateKey function"]
ms.keywords: NtEnumerateKey, ZwEnumerateKey, ZwEnumerateKey routine [Kernel-Mode Driver Architecture], k111_a41e7865-8cac-4dd8-83fb-ca04485feb48.xml, kernel.zwenumeratekey, wdm/NtEnumerateKey, wdm/ZwEnumerateKey
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
 - ZwEnumerateKey
 - wdm/ZwEnumerateKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwEnumerateKey
---

## -description

The **ZwEnumerateKey** routine returns information about a subkey of an open registry key.

## -parameters

### -param KeyHandle [in]

Handle to the registry key that contains the subkeys to be enumerated. The handle is created by a successful call to [ZwCreateKey](./nf-wdm-zwcreatekey.md) or [ZwOpenKey](./nf-wdm-zwopenkey.md).

### -param Index [in]

The index of the subkey that you want information for. If the key has *n* subkeys, the subkeys are numbered from 0 to *n*-1.

### -param KeyInformationClass [in]

Specifies a [KEY_INFORMATION_CLASS](./ne-wdm-_key_information_class.md) enumeration value that determines the type of information to be received by the *KeyInformation* buffer. Set *KeyInformationClass* to one of the following values:

- **KeyBasicInformation**

- **KeyFullInformation**

- **KeyNodeInformation**

If any value not in this list is specified, the routine returns error code STATUS_INVALID_PARAMETER.

### -param KeyInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information. The *KeyInformationClass* parameter determines the type of information provided.

### -param Length [in]

Specifies the size, in bytes, of the *KeyInformation* buffer.

### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the registry-key information. If **ZwEnumerateKey** returns STATUS_SUCCESS, you can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of this variable to determine the size of buffer required to hold the key information.

## -returns

**ZwEnumerateKey** returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error code values include:

| Return code | Description |
|---|---|
| **STATUS_BUFFER_OVERFLOW** | The buffer supplied is too small, and only partial data has been written to the buffer. \**ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_BUFFER_TOO_SMALL** | The buffer supplied is too small, and no data has been written to the buffer. \**ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_INVALID_PARAMETER** | The *KeyInformationClass* parameter is not a valid KEY_INFORMATION_CLASS value. |
| **STATUS_NO_MORE_ENTRIES** | The *Index* value is out of range for the registry key specified by *KeyHandle*. For example, if a key has *n* subkeys, then for any value greater than *n*-1 the routine returns STATUS_NO_MORE_ENTRIES. |

## -remarks

The handle must have been opened with KEY_ENUMERATE_SUB_KEYS access. This is accomplished by passing KEY_ENUMERATE_SUB_KEYS, KEY_READ, or KEY_ALL_ACCESS as the *DesiredAccess* parameter to [ZwCreateKey](./nf-wdm-zwcreatekey.md) or [ZwOpenKey](./nf-wdm-zwopenkey.md).

The *Index* parameter is simply a way to select among subkeys of the key referred to by the *KeyHandle*. Two calls to **ZwEnumerateKey** with the same *Index* are not guaranteed to return the same result.

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtEnumerateKey**" instead of "**ZwEnumerateKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**KEY_BASIC_INFORMATION**](./ns-wdm-_key_basic_information.md)

[**KEY_FULL_INFORMATION**](./ns-wdm-_key_full_information.md)

[KEY_INFORMATION_CLASS](./ne-wdm-_key_information_class.md)

[**KEY_NODE_INFORMATION**](./ns-wdm-_key_node_information.md)

[RtlCheckRegistryKey](./nf-wdm-rtlcheckregistrykey.md)

[RtlCreateRegistryKey](./nf-wdm-rtlcreateregistrykey.md)

[RtlDeleteRegistryValue](./nf-wdm-rtldeleteregistryvalue.md)

[RtlQueryRegistryValues](./nf-wdm-rtlqueryregistryvalues.md)

[RtlWriteRegistryValue](./nf-wdm-rtlwriteregistryvalue.md)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)

[ZwEnumerateValueKey](./nf-wdm-zwenumeratevaluekey.md)

[ZwOpenKey](./nf-wdm-zwopenkey.md)