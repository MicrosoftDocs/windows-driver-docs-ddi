---
UID: NF:wdm.ZwFlushKey
title: ZwFlushKey function (wdm.h)
description: The ZwFlushKey routine forces a registry key to be committed to disk.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwFlushKey function"]
ms.keywords: NtFlushKey, ZwFlushKey, ZwFlushKey routine [Kernel-Mode Driver Architecture], k111_2831bd9f-93c1-4377-9f0e-26d4ef20e095.xml, kernel.zwflushkey, wdm/NtFlushKey, wdm/ZwFlushKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
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
 - ZwFlushKey
 - wdm/ZwFlushKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwFlushKey
---

## -description

The **ZwFlushKey** routine forces a registry key to be committed to disk.

## -parameters

### -param KeyHandle [in]

Handle to the registry key to be flushed to disk. This handle is created by a successful call to [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey).

## -returns

**ZwFlushKey** returns STATUS_SUCCESS if the key information was transferred to disk, or the appropriate error code on failure.

## -remarks

You can flush changes made by [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) or [ZwSetValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey) by calling **ZwFlushKey**. This routine does not return until all the changed data that is associated with *KeyHandle* has been written to disk. **ZwFlushKey** flushes the entire registry hive for the key, which includes every subkey of the key specified.

This routine can flush the entire registry. Accordingly, it can generate a great deal of I/O. Since the system flushes key changes automatically every few seconds, you seldom need to call **ZwFlushKey**.

For more information about working with registry keys, see [Using the Registry in a Driver](/windows-hardware/drivers/kernel/using-the-registry-in-a-driver).

If the call to this function occurs in user mode, you should use the name "**NtFlushKey**" instead of "**ZwFlushKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)

[ZwOpenKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey)

[ZwSetValueKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey)
