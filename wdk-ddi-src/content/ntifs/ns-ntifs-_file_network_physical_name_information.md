---
UID: NS:ntifs._FILE_NETWORK_PHYSICAL_NAME_INFORMATION
title: _FILE_NETWORK_PHYSICAL_NAME_INFORMATION
author: windows-driver-content
description: Contains the full UNC physical pathname for a file or directory on a remote file share.
old-location: ifsk\file_network_physical_name_information.htm
old-project: ifsk
ms.assetid: 04F6A7B1-1198-4E5F-B6A8-70EEABE7CE83
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_NETWORK_PHYSICAL_NAME_INFORMATION, *PFILE_NETWORK_PHYSICAL_NAME_INFORMATION, FILE_NETWORK_PHYSICAL_NAME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_NETWORK_PHYSICAL_NAME_INFORMATION
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PFILE_NETWORK_PHYSICAL_NAME_INFORMATION, FILE_NETWORK_PHYSICAL_NAME_INFORMATION
---

# _FILE_NETWORK_PHYSICAL_NAME_INFORMATION structure



## -description
Contains the full UNC physical pathname for a file or directory on a remote file share.



## -syntax

````
typedef struct _FILE_NETWORK_PHYSICAL_NAME_INFORMATION {
  ULONG FileNameLength;
  WCHAR FileName[1];
} FILE_NETWORK_PHYSICAL_NAME_INFORMATION, *PFILE_NETWORK_PHYSICAL_NAME_INFORMATION;
````


## -struct-fields

### -field FileNameLength

The length, in bytes, of the physical name in <b>FileName</b>.


### -field FileName

The full UNC path of the network file share of the target.


## -remarks
The <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> structure is used to retrieve the network physical name information for a file. This operation can be performed in either of the following ways: 

Call <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>, passing <b>FileNetworkPhysicalNameInformation</b> as the value of <i>FileInformationClass</i> and passing a caller-allocated buffer formatted as a <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> structure for the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the file target for the name information.

Create an IRP with major function code <a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a>. 

The <b>FileName</b> of <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> will contain the network name of the file target handle passed to <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>. The physical network name returned is in the format of <i>\;X:\Server\ShareName\Dir1\Dir2\...\FileName</i>.

If the physical name is longer than the length set in <b>FileNameLength</b>, then STATUS_BUFFER_OVERFLOW is returned  from <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> and <b>FileNameLength</b> is updated with the number of bytes required to hold the entire name string. The count of characters in the name is <b>FileNameLength</b> / <b>sizeof</b>(WCHAR).

The following is an example of querying the network physical name  information of a file target using <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\ne-wdm-_file_information_class.md">FILE_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_NETWORK_PHYSICAL_NAME_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

