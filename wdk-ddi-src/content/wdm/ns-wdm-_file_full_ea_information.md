---
UID: NS:wdm._FILE_FULL_EA_INFORMATION
title: _FILE_FULL_EA_INFORMATION
author: windows-driver-content
description: The FILE_FULL_EA_INFORMATION structure provides extended attribute (EA) information. This structure is used primarily by network drivers.
old-location: kernel\file_full_ea_information.htm
old-project: kernel
ms.assetid: 1b9bbb6a-2dfb-4f3f-8083-62b51a62dec6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _FILE_FULL_EA_INFORMATION, FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION
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
req.alt-api: FILE_FULL_EA_INFORMATION
req.alt-loc: Wdm.h
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
req.typenames: FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_FULL_EA_INFORMATION structure



## -description
The <b>FILE_FULL_EA_INFORMATION</b> structure provides extended attribute (EA) information. This structure is used primarily by network drivers.



## -syntax

````
typedef struct _FILE_FULL_EA_INFORMATION {
  ULONG  NextEntryOffset;
  UCHAR  Flags;
  UCHAR  EaNameLength;
  USHORT EaValueLength;
  CHAR   EaName[1];
} FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

The offset of the next <b>FILE_FULL_EA_INFORMATION</b>-type entry. This member is zero if no other entries follow this one. 


### -field Flags

Can be zero or can be set with FILE_NEED_EA, indicating that the file to which the EA belongs cannot be interpreted without understanding the associated extended attributes.


### -field EaNameLength

The length in bytes of the <b>EaName</b> array. This value does not include a null-terminator to <b>EaName</b>. 


### -field EaValueLength

The length in bytes of each EA value in the array.


### -field EaName

An array of characters naming the EA for this entry.


## -remarks
This structure is longword-aligned. If a set of <b>FILE_FULL_EA_INFORMATION</b> entries is buffered, <b>NextEntryOffset</b> value in each entry, except the last, falls on a longword boundary. 

The value(s) associated with each entry follows the <b>EaName</b> array. That is, an EA's values are located at <b>EaName</b> + (<b>EaNameLength</b> + 1). 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_FULL_EA_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

