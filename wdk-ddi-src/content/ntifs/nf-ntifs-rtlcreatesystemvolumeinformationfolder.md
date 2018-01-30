---
UID: NF:ntifs.RtlCreateSystemVolumeInformationFolder
title: RtlCreateSystemVolumeInformationFolder function
author: windows-driver-content
description: The RtlCreateSystemVolumeInformationFolder routine verifies the existence of the &#0034;System Volume Information&#0034; folder on a file system volume. If the folder is not present, then the folder is created.
old-location: ifsk\rtlcreatesystemvolumeinformationfolder.htm
old-project: ifsk
ms.assetid: bcbbddc7-6675-4555-bd05-588762148554
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rtlcreatesystemvolumeinformationfolder, RtlCreateSystemVolumeInformationFolder, rtlref_f854cbbb-1aa4-4f0a-8d2d-5b160634a155.xml, ntifs/RtlCreateSystemVolumeInformationFolder, RtlCreateSystemVolumeInformationFolder routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows XP and later Windows operating systems.
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
-	RtlCreateSystemVolumeInformationFolder
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlCreateSystemVolumeInformationFolder function


## -description


The <b>RtlCreateSystemVolumeInformationFolder</b> routine verifies the existence of the "System Volume Information" folder on a file system volume. If the folder is not present, then the folder is created. 


## -syntax


````
NTSTATUS RtlCreateSystemVolumeInformationFolder(
  _In_ PCUNICODE_STRING VolumeRootPath
);
````


## -parameters




### -param VolumeRootPath [in]

A pointer to a path to the root of the volume.


## -returns


The <b>RtlCreateSystemVolumeInformationFolder</b> routine returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A temporary buffer required by this function could not be allocated. 

</td>
</tr>
</table> 



## -remarks


The <b>RtlCreateSystemVolumeInformationFolder</b> routine verifies the existence of the "System Volume Information" folder on the given volume. 

If the folder is not present, then the folder is created. If the volume is an NTFS volume, the folder is created with an access control list (<a href="..\wdm\ns-wdm-_acl.md">ACL</a>) containing one access control entry (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>) indicating full access for the local SYSTEM account, and the ACE will have the inheritance bits set. The folder will be created with the FILE_ATTRIBUTE_HIDDEN and FILE_ATTRIBUTE_SYSTEM attributes set.

If the folder is already present and the volume is an NTFS volume, the ACE that indicates full control for SYSTEM will be checked and if necessary modified to have the inheritance bits set.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.



## -see-also

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateSystemVolumeInformationFolder routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

