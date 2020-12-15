---
UID: NF:wdm.ZwFlushKey
title: ZwFlushKey function (wdm.h)
description: The ZwFlushKey routine forces a registry key to be committed to disk.
old-location: kernel\zwflushkey.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwFlushKey function"]
ms.keywords: NtFlushKey, ZwFlushKey, ZwFlushKey routine [Kernel-Mode Driver Architecture], k111_2831bd9f-93c1-4377-9f0e-26d4ef20e095.xml, kernel.zwflushkey, wdm/NtFlushKey, wdm/ZwFlushKey
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
 - NtFlushKey
---

# ZwFlushKey function


## -description

The <b>ZwFlushKey</b> routine forces a registry key to be committed to disk.

## -parameters

### -param KeyHandle 

[in]
Handle to the registry key to be flushed to disk. This handle is created by a successful call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>.

## -returns

<b>ZwFlushKey</b> returns STATUS_SUCCESS if the key information was transferred to disk, or the appropriate error code on failure.

## -remarks

You can flush changes made by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a> by calling <b>ZwFlushKey</b>. This routine does not return until all the changed data that is associated with <i>KeyHandle</i> has been written to disk. <b>ZwFlushKey</b> flushes the entire registry hive for the key, which includes every subkey of the key specified.

<div class="alert"><b>Note</b>    This routine can flush the entire registry. Accordingly, it can generate a great deal of I/O. Since the system flushes key changes automatically every few seconds, you seldom need to call <b>ZwFlushKey</b>.</div>
<div> </div>
For more information about working with registry keys, see <a href="/windows-hardware/drivers/kernel/using-the-registry-in-a-driver">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtFlushKey</b>" instead of "<b>ZwFlushKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwsetvaluekey">ZwSetValueKey</a>
