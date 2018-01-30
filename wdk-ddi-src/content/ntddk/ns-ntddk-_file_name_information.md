---
UID: NS:ntddk._FILE_NAME_INFORMATION
title: "_FILE_NAME_INFORMATION"
author: windows-driver-content
description: The FILE_NAME_INFORMATION structure is used as argument to the ZwQueryInformationFile and ZwSetInformationFile routines.
old-location: kernel\file_name_information.htm
old-project: kernel
ms.assetid: 04ec8e82-d74d-4827-8533-aa57e3638a45
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PFILE_NAME_INFORMATION, kernel.file_name_information, _FILE_NAME_INFORMATION, *PFILE_NAME_INFORMATION, ntddk/FILE_NAME_INFORMATION, PFILE_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], kstruct_b_075348cd-50d6-450f-9a9d-a5ad8fd985e3.xml, FILE_NAME_INFORMATION structure [Kernel-Mode Driver Architecture], FILE_NAME_INFORMATION, PFILE_NAME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	FILE_NAME_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILE_NAME_INFORMATION, FILE_NAME_INFORMATION"
---

# _FILE_NAME_INFORMATION structure


## -description


The <b>FILE_NAME_INFORMATION</b> structure is used as argument to the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> and <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> routines.


## -syntax


````
typedef struct _FILE_NAME_INFORMATION {
  ULONG FileNameLength;
  WCHAR FileName[1];
} FILE_NAME_INFORMATION, *PFILE_NAME_INFORMATION;
````


## -struct-fields




### -field FileNameLength

Specifies the length, in bytes, of the file name string.


### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.


## -remarks


The <b>ZwQueryInformationFile</b> routine uses this structure to return the file name string to the caller. For more information about the form of the name returned, see <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>.

Callers of <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> can use this structure to specify a new short name for a file.



## -see-also

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_NAME_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

