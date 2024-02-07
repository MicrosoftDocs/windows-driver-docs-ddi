---
UID: NF:wdm.ZwOpenFile
title: ZwOpenFile function (wdm.h)
description: The ZwOpenFile routine in wdm.h opens an existing file, directory, device, or volume. Once the handle pointed to is no longer in use, the driver must close it.
tech.root: kernel
ms.date: 12/14/2022
author: lorihollasch
keywords: ["ZwOpenFile function"]
ms.keywords: NtOpenFile, ZwOpenFile, ZwOpenFile routine [Kernel-Mode Driver Architecture], k111_efde7b0f-a00d-47c8-8a34-ae22fb909718.xml, kernel.zwopenfile, wdm/NtOpenFile, wdm/ZwOpenFile
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwOpenFile
 - wdm/ZwOpenFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenFile
---

## -description

The **ZwOpenFile** routine opens an existing file, directory, device, or volume.

## -parameters

### -param FileHandle [out]

Pointer to a HANDLE variable that receives a handle to the file.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object. For more information, see the *DesiredAccess* parameter of [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md).

### -param ObjectAttributes [in]

Pointer to an [OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that specifies the object name and other attributes. Use [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls **InitializeObjectAttributes**.

### -param IoStatusBlock [out]

Pointer to an [IO_STATUS_BLOCK](./ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the requested operation.

### -param ShareAccess [in]

Specifies the type of share access for the file. For more information, see the *ShareAccess* parameter of [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md).

### -param OpenOptions [in]

Specifies the options to apply when opening the file. For more information, see the *CreateOptions* parameter of [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md).

## -returns

**ZwOpenFile** returns STATUS_SUCCESS or the appropriate NTSTATUS error code. In the latter case, the caller can find more information about the cause of the failure by checking the *IoStatusBlock* parameter.

## -remarks

**ZwOpenFile** supplies a handle that the caller can use to manipulate a file's data, or the file object's state and attributes. **ZwOpenFile** provides a subset of the functionality provided by [ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md). For more information, see [Using Files in a Driver](/windows-hardware/drivers/kernel/using-files-in-a-driver).

Once the handle pointed to by *FileHandle* is no longer in use, the driver must call [ZwClose](../ntifs/nf-ntifs-ntclose.md) to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

Callers of **ZwOpenFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

If the call to this function occurs in user mode, you should use the name "**NtOpenFile**" instead of "**ZwOpenFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)