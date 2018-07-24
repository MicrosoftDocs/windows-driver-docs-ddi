---
UID: NE:ntddtape._TAPE_DRIVE_PROBLEM_TYPE
title: "_TAPE_DRIVE_PROBLEM_TYPE"
author: windows-driver-content
description: The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive.
old-location: storage\tape_drive_problem_type.htm
tech.root: storage
ms.assetid: c2732686-5f95-41fd-8e47-8acf6900a44b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: TAPE_DRIVE_PROBLEM_TYPE, TAPE_DRIVE_PROBLEM_TYPE enumeration [Storage Devices], TapeDriveCleanDriveNow, TapeDriveHardwareError, TapeDriveMediaLifeExpired, TapeDriveProblemNone, TapeDriveReadError, TapeDriveReadWarning, TapeDriveReadWriteError, TapeDriveReadWriteWarning, TapeDriveScsiConnectionError, TapeDriveSnappedTape, TapeDriveTimetoClean, TapeDriveUnsupportedMedia, TapeDriveWriteError, TapeDriveWriteWarning, _TAPE_DRIVE_PROBLEM_TYPE, ntddtape/TAPE_DRIVE_PROBLEM_TYPE, ntddtape/TapeDriveCleanDriveNow, ntddtape/TapeDriveHardwareError, ntddtape/TapeDriveMediaLifeExpired, ntddtape/TapeDriveProblemNone, ntddtape/TapeDriveReadError, ntddtape/TapeDriveReadWarning, ntddtape/TapeDriveReadWriteError, ntddtape/TapeDriveReadWriteWarning, ntddtape/TapeDriveScsiConnectionError, ntddtape/TapeDriveSnappedTape, ntddtape/TapeDriveTimetoClean, ntddtape/TapeDriveUnsupportedMedia, ntddtape/TapeDriveWriteError, ntddtape/TapeDriveWriteWarning, storage.tape_drive_problem_type, structs-tape_e5fef478-5c62-4cbf-adc1-8f0cc6eabb8e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddtape.h
req.include-header: Minitape.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddtape.h
api_name:
-	TAPE_DRIVE_PROBLEM_TYPE
product:
- Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# _TAPE_DRIVE_PROBLEM_TYPE enumeration


## -description


The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive. 


## -enum-fields




### -field TapeDriveProblemNone

Indicates that there is no tape drive problem.


### -field TapeDriveReadWriteWarning

Indicates that the tape drive is having problems doing reads or writes. This is a warning.


### -field TapeDriveReadWriteError

Indicates that the tape drive is having problems doing reads or writes. This is a severe error.


### -field TapeDriveReadWarning

Indicates that the tape drive is having problems doing reads. This is a warning.


### -field TapeDriveWriteWarning

Indicates that the tape drive is having problems doing writes. This is a warning.


### -field TapeDriveReadError

Indicates that the tape drive is having problems doing reads. This is a severe error.


### -field TapeDriveWriteError

Indicates that the tape drive is having problems doing writes. This is a severe error.


### -field TapeDriveHardwareError

Indicates that the tape drive had a hardware error.


### -field TapeDriveUnsupportedMedia

Indicates that the media format is not supported.


### -field TapeDriveScsiConnectionError

Indicates that there is a SCSI cable or connection error.


### -field TapeDriveTimetoClean

Indicates that the tape drive requires cleaning.


### -field TapeDriveCleanDriveNow

Indicates that the tape drive requires cleaning.


### -field TapeDriveMediaLifeExpired

Indicates that the media life has expired. Media needs to be replaced.


### -field TapeDriveSnappedTape

Indicates that the tape has snapped.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567977">TAPE_WMI_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567957">TapeMiniWMIControl</a>
 

 

