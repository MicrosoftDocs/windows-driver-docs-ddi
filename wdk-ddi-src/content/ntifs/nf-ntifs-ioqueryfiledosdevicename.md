---
UID: NF:ntifs.IoQueryFileDosDeviceName
title: IoQueryFileDosDeviceName function (ntifs.h)
description: The IoQueryFileDosDeviceName routine retrieves an MS-DOS device name for a file.
old-location: ifsk\ioqueryfiledosdevicename.htm
tech.root: ifsk
ms.assetid: 8574e5cf-5bbf-4606-931f-e27b2aa7b7fa
ms.date: 04/16/2018
keywords: ["IoQueryFileDosDeviceName function"]
ms.keywords: IoQueryFileDosDeviceName, IoQueryFileDosDeviceName routine [Installable File System Drivers], ifsk.ioqueryfiledosdevicename, ioref_4bc807ab-ce5e-415c-8f86-50cf3783d233.xml, ntifs/IoQueryFileDosDeviceName
f1_keywords:
 - "ntifs/IoQueryFileDosDeviceName"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting withWindows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoQueryFileDosDeviceName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoQueryFileDosDeviceName function


## -description


The <b>IoQueryFileDosDeviceName</b> routine retrieves an MS-DOS device name for a file. 


## -parameters




### -param FileObject [in]

Pointer to a file object for the file. 


### -param ObjectNameInformation [out]

A returned pointer to a newly allocated <b>OBJECT_NAME_INFORMATION</b> structure. This structure is filled in on successful return with the MS-DOS device name information. The structure is defined as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _OBJECT_NAME_INFORMATION {
    UNICODE_STRING Name;
} OBJECT_NAME_INFORMATION, *POBJECT_NAME_INFORMATION;</pre>
</td>
</tr>
</table></span></div>
<div class="alert"><b>Note</b>    This structure must eventually be freed by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>.</div>
<div> </div>

## -returns



<b>IoQueryFileDosDeviceName</b> returns STATUS_SUCCESS or an error NTSTATUS value, such as STATUS_INSUFFICIENT_RESOURCES. 




## -remarks



For more information about MS-DOS names, see the Files and I/O section of the Platform Software Development Kit (SDK) documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

