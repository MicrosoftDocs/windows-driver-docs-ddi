---
UID: NF:wdm.ZwLoadDriver
title: ZwLoadDriver function (wdm.h)
description: The ZwLoadDriver routine loads a driver into the system.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwLoadDriver function"]
ms.keywords: NtLoadDriver, ZwLoadDriver, ZwLoadDriver routine [Kernel-Mode Driver Architecture], k111_b421f181-1a7d-4122-a73c-604f6b98686d.xml, kernel.zwloaddriver, wdm/NtLoadDriver, wdm/ZwLoadDriver
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
 - ZwLoadDriver
 - wdm/ZwLoadDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwLoadDriver
---

## -description

The **ZwLoadDriver** routine loads a driver into the system.

## -parameters

### -param DriverServiceName [in]

Pointer to a counted Unicode string that specifies a path to the driver's registry key, \Registry\Machine\System\CurrentControlSet\Services\\<*DriverName*>, where <*DriverName*> is the name of the driver.

## -returns

**ZwLoadDriver** returns STATUS_SUCCESS or an appropriate error NTSTATUS value.

## -remarks

**ZwLoadDriver** dynamically loads a device or file system driver into the currently running system.

If the system is running in safe mode, and the driver fails to load because it is not on the safe mode list, **ZwLoadDriver** returns STATUS_SUCCESS.

A minifilter should use [FltLoadFilter](/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter) instead of **ZwLoadDriver** to load a supporting minifilter.

If the call to the **ZwLoadDriver** function occurs in user mode, you should use the name "**NtLoadDriver**" instead of "**ZwLoadDriver**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[FltLoadFilter](/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter)

[RtlInitUnicodeString](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitunicodestring)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwUnloadDriver](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunloaddriver)
