---
UID: NS:wdm._FILE_IO_PRIORITY_HINT_INFORMATION
title: _FILE_IO_PRIORITY_HINT_INFORMATION
author: windows-driver-content
description: The FILE_IO_PRIORITY_HINT_INFORMATION structure is used by the ZwQueryInformationFile and ZwSetInformationFile routines to query and set the default IRP priority hint for requests on the specified file handle.
old-location: kernel\file_io_priority_hint_information.htm
old-project: kernel
ms.assetid: 55f88d42-8411-49f0-bc40-7ccc268b3cc5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PFILE_IO_PRIORITY_HINT_INFORMATION, kstruct_b_babd0cbe-1870-4d71-86c5-06c438691202.xml, wdm/PFILE_IO_PRIORITY_HINT_INFORMATION, PFILE_IO_PRIORITY_HINT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_IO_PRIORITY_HINT_INFORMATION, *PFILE_IO_PRIORITY_HINT_INFORMATION, wdm/FILE_IO_PRIORITY_HINT_INFORMATION, kernel.file_io_priority_hint_information, FILE_IO_PRIORITY_HINT_INFORMATION structure [Kernel-Mode Driver Architecture], FILE_IO_PRIORITY_HINT_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	FILE_IO_PRIORITY_HINT_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_IO_PRIORITY_HINT_INFORMATION, *PFILE_IO_PRIORITY_HINT_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_IO_PRIORITY_HINT_INFORMATION structure


## -description


The <b>FILE_IO_PRIORITY_HINT_INFORMATION</b> structure is used by the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> and <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> routines to query and set the default IRP <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint</a> for requests on the specified file handle.


## -syntax


````
typedef struct _FILE_IO_PRIORITY_HINT_INFORMATION {
  IO_PRIORITY_HINT PriorityHint;
} FILE_IO_PRIORITY_HINT_INFORMATION, *PFILE_IO_PRIORITY_HINT_INFORMATION;
````


## -struct-fields




### -field PriorityHint

Specifies the <a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a> value that indicates the priority hint for a file handle.


## -remarks


For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.



## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>

<a href="..\wdm\ne-wdm-_io_priority_hint.md">IO_PRIORITY_HINT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_IO_PRIORITY_HINT_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

