---
UID: NF:ntifs.FsRtlAreVolumeStartupApplicationsComplete
title: FsRtlAreVolumeStartupApplicationsComplete function
author: windows-driver-content
description: The FsRtlAreVolumeStartupApplicationsComplete function determines whether volume startup applications have completed processing.
old-location: ifsk\fsrtlarevolumestartupapplicationscomplete.htm
old-project: ifsk
ms.assetid: a6ee1b04-7f62-452c-92b7-7325278bcd17
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/FsRtlAreVolumeStartupApplicationsComplete, fsrtlref_c0858a3d-5e61-4ba3-bbaf-9ec881042d6a.xml, ifsk.fsrtlarevolumestartupapplicationscomplete, FsRtlAreVolumeStartupApplicationsComplete function [Installable File System Drivers], FsRtlAreVolumeStartupApplicationsComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlAreVolumeStartupApplicationsComplete
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAreVolumeStartupApplicationsComplete function


## -description


The <b>FsRtlAreVolumeStartupApplicationsComplete</b> function determines whether volume startup applications have completed processing.


## -syntax


````
BOOLEAN FsRtlAreVolumeStartupApplicationsComplete(void);
````


## -parameters






## -returns



<b>FsRtlAreVolumeStartupApplicationsComplete</b> returns <b>TRUE</b> if all volume startup applications for the system have completed their startup processing, <b>FALSE</b> otherwise.




## -remarks



The <b>FsRtlAreVolumeStartupApplicationsComplete</b> function returns <b>TRUE</b> if session manager (Smss.exe) has completed running all startup applications for the system volume(s), <b>FALSE</b> otherwise.

You can use this information to modify the behavior of file system drivers.  For example, a file system driver can adversely affect Autochk.exe if the driver starts its processing before Autochck.exe has fully completed.  If <b>FsRtlAreVolumeStartupApplicationsComplete</b> returns <b>TRUE</b>, Autochk.exe is guaranteed to have fully completed.

To retrieve information about the volume that a minifilter instance is attached to, see <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>. 

To retrieve information about the volume associated with a given file, directory, or storage device, see <a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-zwqueryvolumeinformationfile.md">ZwQueryVolumeInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md">FltQueryVolumeInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAreVolumeStartupApplicationsComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

