---
UID: NS:wdm._FILE_NETWORK_OPEN_INFORMATION
title: "_FILE_NETWORK_OPEN_INFORMATION"
author: windows-driver-content
description: The FILE_NETWORK_OPEN_INFORMATION structure is used as an argument to ZwQueryInformationFile.
old-location: kernel\file_network_open_information.htm
old-project: kernel
ms.assetid: 742fa221-70c8-410a-a582-aedf28872ada
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFILE_NETWORK_OPEN_INFORMATION, FILE_NETWORK_OPEN_INFORMATION, FILE_NETWORK_OPEN_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_NETWORK_OPEN_INFORMATION, PFILE_NETWORK_OPEN_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_NETWORK_OPEN_INFORMATION, kernel.file_network_open_information, kstruct_b_761510b6-751c-457d-a516-cce0d9fa3027.xml, wdm/FILE_NETWORK_OPEN_INFORMATION, wdm/PFILE_NETWORK_OPEN_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	FILE_NETWORK_OPEN_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_NETWORK_OPEN_INFORMATION, *PFILE_NETWORK_OPEN_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_NETWORK_OPEN_INFORMATION structure


## -description


The <b>FILE_NETWORK_OPEN_INFORMATION</b> structure is used as an argument to <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>. 


## -syntax


````
typedef struct _FILE_NETWORK_OPEN_INFORMATION {
  LARGE_INTEGER CreationTime;
  LARGE_INTEGER LastAccessTime;
  LARGE_INTEGER LastWriteTime;
  LARGE_INTEGER ChangeTime;
  LARGE_INTEGER AllocationSize;
  LARGE_INTEGER EndOfFile;
  ULONG         FileAttributes;
} FILE_NETWORK_OPEN_INFORMATION, *PFILE_NETWORK_OPEN_INFORMATION;
````


## -struct-fields




### -field CreationTime

Specifies the time that the file was created.


### -field LastAccessTime

Specifies the time that the file was last accessed.


### -field LastWriteTime

Specifies he time that the file was last written to.


### -field ChangeTime

Specifies the time that the file was last changed.


### -field AllocationSize

Specifies the file allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device.


### -field EndOfFile

Specifies the absolute end-of-file position as a byte offset from the start of the file. <b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, <b>EndOfFile</b> is the offset to the byte immediately following the last valid byte in the file.


### -field FileAttributes

Specifies one or more FILE_ATTRIBUTE_<i>XXX</i> flags. For descriptions of these flags, see the documentation of the <b>GetFileAttributes</b> function in the Microsoft Windows SDK.


## -remarks



FILE_READ_ATTRIBUTES access to the file is required to query this information.

Time values <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, and <b>ChangeTime</b> are expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.

This structure must be aligned on a LONGLONG (8-byte) boundary.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_NETWORK_OPEN_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

