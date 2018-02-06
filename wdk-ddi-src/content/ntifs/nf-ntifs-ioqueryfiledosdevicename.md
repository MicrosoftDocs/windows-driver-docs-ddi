---
UID: NF:ntifs.IoQueryFileDosDeviceName
title: IoQueryFileDosDeviceName function
author: windows-driver-content
description: The IoQueryFileDosDeviceName routine retrieves an MS-DOS device name for a file.
old-location: ifsk\ioqueryfiledosdevicename.htm
old-project: ifsk
ms.assetid: 8574e5cf-5bbf-4606-931f-e27b2aa7b7fa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoQueryFileDosDeviceName routine [Installable File System Drivers], ifsk.ioqueryfiledosdevicename, ioref_4bc807ab-ce5e-415c-8f86-50cf3783d233.xml, IoQueryFileDosDeviceName, ntifs/IoQueryFileDosDeviceName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoQueryFileDosDeviceName
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoQueryFileDosDeviceName function


## -description


The <b>IoQueryFileDosDeviceName</b> routine retrieves an MS-DOS device name for a file. 


## -syntax


````
NTSTATUS IoQueryFileDosDeviceName(
  _In_  PFILE_OBJECT             FileObject,
  _Out_ POBJECT_NAME_INFORMATION *ObjectNameInformation
);
````


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
</table></span></div><div class="alert"><b>Note</b>    This structure must eventually be freed by calling <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>.</div><div> </div>

## -returns


<b>IoQueryFileDosDeviceName</b> returns STATUS_SUCCESS or an error NTSTATUS value, such as STATUS_INSUFFICIENT_RESOURCES. 



## -remarks


For more information about MS-DOS names, see the Files and I/O section of the Platform Software Development Kit (SDK) documentation. 



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoQueryFileDosDeviceName routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

