---
UID: NF:ntddk.FsRtlIsTotalDeviceFailure
title: FsRtlIsTotalDeviceFailure function
author: windows-driver-content
description: The FsRtlIsTotalDeviceFailure routine determines whether a media or other hardware failure has occurred.
old-location: ifsk\fsrtlistotaldevicefailure.htm
old-project: ifsk
ms.assetid: 6d1a39ea-bdc0-47e2-94a5-69554f4b38c4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlIsTotalDeviceFailure, FsRtlIsTotalDeviceFailure routine [Installable File System Drivers], fsrtlref_b4ec70b9-8a76-4e47-905a-54238a0b9173.xml, ifsk.fsrtlistotaldevicefailure, ntddk/FsRtlIsTotalDeviceFailure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlIsTotalDeviceFailure
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# FsRtlIsTotalDeviceFailure function


## -description


The <b>FsRtlIsTotalDeviceFailure</b> routine determines whether a media or other hardware failure has occurred.


## -syntax


````
BOOLEAN FsRtlIsTotalDeviceFailure(
  _In_ NTSTATUS Status
);
````


## -parameters




### -param Status [in]

Specifies the current NTSTATUS value, usually within a file system's or fault-tolerant disk driver's completion routine.


## -returns



The <b>FsRtlIsTotalDeviceFailure</b> routine returns <b>TRUE</b> if an I/O request failed because the physical device has failed.




## -remarks



If <b>FsRtlIsTotalDeviceFailure</b> returns <b>TRUE</b>, a higher-level driver, such as a file system or fault-tolerant disk driver, usually logs an error before completing the IRP.

<b>FsRtlIsTotalDeviceFailure</b> does not return <b>TRUE</b> for either of the status values STATUS_DEVICE_DATA_ERROR and STATUS_CRC_ERROR, which are assumed to indicate a sector failure rather than a total disk failure.

For more information about handling device failure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnormalizentstatus~r1.md">FsRtlNormalizeNtstatus</a>



<a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisntstatusexpected.md">FsRtlIsNtstatusExpected</a>



 

 


