---
UID: NF:ntifs.FsRtlAreVolumeStartupApplicationsComplete
title: FsRtlAreVolumeStartupApplicationsComplete function (ntifs.h)
description: The FsRtlAreVolumeStartupApplicationsComplete function determines whether volume startup applications have completed processing.
old-location: ifsk\fsrtlarevolumestartupapplicationscomplete.htm
tech.root: ifsk
ms.assetid: a6ee1b04-7f62-452c-92b7-7325278bcd17
ms.date: 07/24/20209
keywords: ["FsRtlAreVolumeStartupApplicationsComplete function"]
ms.keywords: FsRtlAreVolumeStartupApplicationsComplete, FsRtlAreVolumeStartupApplicationsComplete function [Installable File System Drivers], fsrtlref_c0858a3d-5e61-4ba3-bbaf-9ec881042d6a.xml, ifsk.fsrtlarevolumestartupapplicationscomplete, ntifs/FsRtlAreVolumeStartupApplicationsComplete
f1_keywords:
 - "ntifs/FsRtlAreVolumeStartupApplicationsComplete"
 - "FsRtlAreVolumeStartupApplicationsComplete"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlAreVolumeStartupApplicationsComplete
targetos: Windows
req.typenames: 
---

# FsRtlAreVolumeStartupApplicationsComplete function

## -description

The **FsRtlAreVolumeStartupApplicationsComplete** function determines whether volume startup applications have completed processing.

## -returns

**FsRtlAreVolumeStartupApplicationsComplete** returns **TRUE** if all volume startup applications for the system have completed their startup processing, **FALSE** otherwise.

## -remarks

The **FsRtlAreVolumeStartupApplicationsComplete** function returns **TRUE** if session manager (*Smss.exe*) has completed running all startup applications for the system volume(s), **FALSE** otherwise.

You can use this information to modify the behavior of file system drivers. For example, a file system driver can adversely affect *Autochk.exe* if the driver starts its processing before *Autochck.exe* has fully completed. If **FsRtlAreVolumeStartupApplicationsComplete** returns **TRUE**, *Autochk.exe* is guaranteed to have fully completed.

To retrieve information about the volume that a minifilter instance is attached to, see [**FltQueryVolumeInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation).

To retrieve information about the volume associated with a given file, directory, or storage device, see [**ZwQueryVolumeInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwqueryvolumeinformationfile).

## -see-also

[**FltQueryVolumeInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation)

[**ZwQueryVolumeInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwqueryvolumeinformationfile)
