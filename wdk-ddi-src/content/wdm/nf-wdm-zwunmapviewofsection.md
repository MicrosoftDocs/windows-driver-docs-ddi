---
UID: NF:wdm.ZwUnmapViewOfSection
title: ZwUnmapViewOfSection function (wdm.h)
description: The ZwUnmapViewOfSection routine unmaps a view of a section from the virtual address space of a subject process.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["ZwUnmapViewOfSection function"]
ms.keywords: NtUnmapViewOfSection, ZwUnmapViewOfSection, ZwUnmapViewOfSection routine [Kernel-Mode Driver Architecture], k111_4353325c-d2a1-47b3-b58a-b62929c417f9.xml, kernel.zwunmapviewofsection, wdm/NtUnmapViewOfSection, wdm/ZwUnmapViewOfSection
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
 - ZwUnmapViewOfSection
 - wdm/ZwUnmapViewOfSection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwUnmapViewOfSection
---

## -description

The **ZwUnmapViewOfSection** routine unmaps a [view](/windows-hardware/drivers/kernel/section-objects-and-views) of a section from the virtual address space of a subject process.

## -parameters

### -param ProcessHandle [in]

Handle to a process object that was previously passed to [ZwMapViewOfSection](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmapviewofsection).

### -param BaseAddress [in, optional]

Pointer to the base virtual address of the view to unmap. This value can be any virtual address within the view.

## -returns

**ZwUnmapViewOfSection** returns an NTSTATUS value. Possible return values include:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The routine successfully performed the requested operation. |
| **STATUS_ACCESS_DENIED** | The caller does not have access rights to the process object or to the base virtual address of the view. |

## -remarks

This routine unmaps the entire view of the section that contains *BaseAddress* from the virtual address space of the specified process—even if *BaseAddress* does not point to the beginning of the view.

On return from **ZwUnmapViewOfSection**, the virtual-address region occupied by the view is no longer reserved and is available to map other views or private pages. If the view was also the last reference to the underlying section, all committed pages in the section are decommitted, and the section is deleted.

If the call to this function occurs in user mode, you should use the name "[NtUnmapViewOfSection](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwunmapviewofsection)" instead of "**ZwUnmapViewOfSection**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwMapViewOfSection](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwmapviewofsection)

[ZwOpenSection](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopensection)
