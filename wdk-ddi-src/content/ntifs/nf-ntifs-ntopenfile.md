---
UID: NF:ntifs.NtOpenFile
title: NtOpenFile function (ntifs.h)
description: The ZwOpenFile routine opens an existing file, directory, device, or volume.
old-location: kernel\zwopenfile.htm
tech.root: kernel
ms.assetid: 7c07d250-6287-4dd3-96f9-f301bad8b6f3
ms.date: 04/30/2018
ms.keywords: NtOpenFile, ZwOpenFile, ZwOpenFile routine [Kernel-Mode Driver Architecture], k111_efde7b0f-a00d-47c8-8a34-ae22fb909718.xml, kernel.zwopenfile, wdm/NtOpenFile, wdm/ZwOpenFile
ms.topic: function
f1_keywords:
 - "ntifs/ZwOpenFile"
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwOpenFile
- NtOpenFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtOpenFile function


## -description


The <b>NtOpenFile</b> routine opens an existing file, directory, device, or volume.


## -parameters




### -param FileHandle [out]

Pointer to a HANDLE variable that receives a handle to the file.


### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a>.


### -param ObjectAttributes [in]

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


### -param IoStatusBlock [out]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation.


### -param ShareAccess [in]

Specifies the type of share access for the file. For more information, see the <i>ShareAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a>.


### -param OpenOptions [in]

Specifies the options to apply when opening the file. For more information, see the <i>CreateOptions</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a>.


## -returns



<b>NtOpenFile</b> returns STATUS_SUCCESS or the appropriate NTSTATUS error code. In the latter case, the caller can find more information about the cause of the failure by checking the <i>IoStatusBlock</i> parameter.




## -remarks



<b>NtOpenFile</b> supplies a handle that the caller can use to manipulate a file's data, or the file object's state and attributes. <b>NtOpenFile</b> provides a subset of the functionality provided by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">NtCreateFile</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-files-in-a-driver">Using Files in a Driver</a>.

Once the handle pointed to by <i>FileHandle</i> is no longer in use, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>. 

Callers of <b>NtOpenFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/disabling-apcs">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenFile</b>" instead of "<b>ZwOpenFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>
 

 

