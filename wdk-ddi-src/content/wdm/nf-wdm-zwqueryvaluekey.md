---
UID: NF:wdm.ZwQueryValueKey
title: ZwQueryValueKey function (wdm.h)
description: The ZwQueryValueKey routine returns a value entry for a registry key.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["ZwQueryValueKey function"]
ms.keywords: NtQueryValueKey, ZwQueryValueKey, ZwQueryValueKey routine [Kernel-Mode Driver Architecture], k111_f51b0b92-f768-4f96-9f2a-d1322fd02517.xml, kernel.zwqueryvaluekey, wdm/NtQueryValueKey, wdm/ZwQueryValueKey
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
 - ZwQueryValueKey
 - wdm/ZwQueryValueKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryValueKey
---

## -description

The **ZwQueryValueKey** routine returns a value entry for a registry key.

## -parameters

### -param KeyHandle [in]

Handle to the key to read value entries from. This handle is created by a successful call to [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey).

### -param ValueName [in]

Pointer to the name of the value entry to obtain data for.

### -param KeyValueInformationClass [in]

A [KEY_VALUE_INFORMATION_CLASS](/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class) value that determines the type of information returned in the *KeyValueInformation* buffer.

### -param KeyValueInformation [out, optional]

Pointer to a caller-allocated buffer that receives the requested information.

### -param Length [in]

Specifies the size, in bytes, of the *KeyValueInformation* buffer.

### -param ResultLength [out]

Pointer to a variable that receives the size, in bytes, of the key information. If the **ZwQueryValueKey** routine returns STATUS_SUCCESS, callers can use the value of this variable to determine the amount of data returned. If the routine returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, callers can use the value of this variable to determine the size of buffer required to hold the key information.

## -returns

**ZwQueryValueKey** returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible error code values include:

| Return code | Description |
|---|---|
| **STATUS_OBJECT_NAME_NOT_FOUND** | The registry value was not available. |
| **STATUS_BUFFER_OVERFLOW** | The buffer supplied is too small, and only partial data has been written to the buffer. *ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_BUFFER_TOO_SMALL** | The buffer supplied is too small, and no data has been written to the buffer. *ResultLength* is set to the minimum size required to hold the requested information. |
| **STATUS_INVALID_PARAMETER** | The *KeyInformationClass* parameter is not a valid **KEY_VALUE_INFORMATION_CLASS** value. |

## -remarks

The *KeyHandle* passed to **ZwQueryValueKey** must have been opened with KEY_QUERY_VALUE access. This is accomplished by passing KEY_QUERY_VALUE, KEY_READ, or KEY_ALL_ACCESS as the *DesiredAccess* parameter to [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey).

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtQueryValueKey**" instead of "**ZwQueryValueKey**".
For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**KEY_VALUE_BASIC_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information)

[**KEY_VALUE_FULL_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information)

[KEY_VALUE_INFORMATION_CLASS](/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_value_information_class)

[**KEY_VALUE_PARTIAL_INFORMATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)

[ZwEnumerateValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey)

[ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey)
