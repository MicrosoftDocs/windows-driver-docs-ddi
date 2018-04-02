---
UID: NF:ntifs.FsRtlAreVolumeStartupApplicationsComplete
title: FsRtlAreVolumeStartupApplicationsComplete function
author: windows-driver-content
description: The FsRtlAreVolumeStartupApplicationsComplete function determines whether volume startup applications have completed processing.
old-location: ifsk\fsrtlarevolumestartupapplicationscomplete.htm
old-project: ifsk
ms.assetid: a6ee1b04-7f62-452c-92b7-7325278bcd17
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlAreVolumeStartupApplicationsComplete, FsRtlAreVolumeStartupApplicationsComplete function [Installable File System Drivers], fsrtlref_c0858a3d-5e61-4ba3-bbaf-9ec881042d6a.xml, ifsk.fsrtlarevolumestartupapplicationscomplete, ntifs/FsRtlAreVolumeStartupApplicationsComplete
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlAreVolumeStartupApplicationsComplete
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlAreVolumeStartupApplicationsComplete function


## -description


The <b>FsRtlAreVolumeStartupApplicationsComplete</b> function determines whether volume startup applications have completed processing.


## -parameters






## -returns



<b>FsRtlAreVolumeStartupApplicationsComplete</b> returns <b>TRUE</b> if all volume startup applications for the system have completed their startup processing, <b>FALSE</b> otherwise.




## -remarks



The <b>FsRtlAreVolumeStartupApplicationsComplete</b> function returns <b>TRUE</b> if session manager (Smss.exe) has completed running all startup applications for the system volume(s), <b>FALSE</b> otherwise.

You can use this information to modify the behavior of file system drivers.  For example, a file system driver can adversely affect Autochk.exe if the driver starts its processing before Autochck.exe has fully completed.  If <b>FsRtlAreVolumeStartupApplicationsComplete</b> returns <b>TRUE</b>, Autochk.exe is guaranteed to have fully completed.

To retrieve information about the volume that a minifilter instance is attached to, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>. 

To retrieve information about the volume associated with a given file, directory, or storage device, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

