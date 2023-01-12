---
UID: NF:wdm.ZwUnloadDriver
title: ZwUnloadDriver function (wdm.h)
description: The ZwUnloadDriver routine unloads a driver from the system.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["ZwUnloadDriver function"]
ms.keywords: NtUnloadDriver, ZwUnloadDriver, ZwUnloadDriver routine [Kernel-Mode Driver Architecture], k111_72ac4415-d46c-4ea2-9d6c-d66903082808.xml, kernel.zwunloaddriver, wdm/NtUnloadDriver, wdm/ZwUnloadDriver
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
 - ZwUnloadDriver
 - wdm/ZwUnloadDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwUnloadDriver
---

## -description

The **ZwUnloadDriver** routine unloads a driver from the system. Use this routine with extreme caution (see the **Remarks** section below).

## -parameters

### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, `\Registry\Machine\System\CurrentControlSet\Services\<DriverName>`, where *DriverName* is the name of the driver.

## -returns

**ZwUnloadDriver** returns STATUS_SUCCESS or an error NTSTATUS value such as STATUS_INVALID_DEVICE_REQUEST.

If the driver specified in *DriverServiceName* has no *DriverUnload* callback routine set in its [**DRIVER_OBJECT**](./ns-wdm-_driver_object.md) structure, **ZwUnloadDriver** returns STATUS_INVALID_DEVICE_REQUEST.

## -remarks

**ZwUnloadDriver** dynamically unloads a device or file system driver from the currently running system. It is not recommended that a driver call **ZwUnloadDriver** on itself.

A file system filter driver cannot safely be unloaded from a running system. Thus a filter should only use **ZwUnloadDriver** for debugging purposes. It should not call this routine in a retail version of the filter.

If *DriverName* is the name of a PnP device driver, **ZwUnloadDriver** returns STATUS_INVALID_DEVICE_REQUEST and does not unload the driver.

A minifilter should use [FltUnloadFilter](../fltkernel/nf-fltkernel-fltunloadfilter.md) instead of **ZwUnloadDriver** to unload a supporting minifilter.

If the call to the **ZwUnloadDriver** function occurs in user mode, you should use the name "[NtUnloadDriver](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunloaddriver)" instead of "**ZwUnloadDriver**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[FltUnloadFilter](../fltkernel/nf-fltkernel-fltunloadfilter.md)

[RtlInitUnicodeString](./nf-wdm-rtlinitunicodestring.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)