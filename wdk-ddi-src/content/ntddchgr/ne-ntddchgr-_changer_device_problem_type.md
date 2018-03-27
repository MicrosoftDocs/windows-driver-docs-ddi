---
UID: NE:ntddchgr._CHANGER_DEVICE_PROBLEM_TYPE
title: "_CHANGER_DEVICE_PROBLEM_TYPE"
author: windows-driver-content
description: The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the ChangerPerformDiagnostics routine.
old-location: storage\changer_device_problem_type.htm
old-project: storage
ms.assetid: 2ba267ad-cfd7-4a19-9ecb-16be9187406a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCHANGER_DEVICE_PROBLEM_TYPE, CHANGER_DEVICE_PROBLEM_TYPE, CHANGER_DEVICE_PROBLEM_TYPE enumeration [Storage Devices], DeviceProblemCHMError, DeviceProblemCHMMoveError, DeviceProblemCHMZeroError, DeviceProblemCalibrationError, DeviceProblemCartridgeEjectError, DeviceProblemCartridgeInsertError, DeviceProblemDoorOpen, DeviceProblemDriveError, DeviceProblemGripperError, DeviceProblemHardware, DeviceProblemNone, DeviceProblemPositionError, DeviceProblemSensorError, DeviceProblemTargetFailure, PCHANGER_DEVICE_PROBLEM_TYPE, PCHANGER_DEVICE_PROBLEM_TYPE enumeration pointer [Storage Devices], _CHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/CHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/DeviceProblemCHMError, ntddchgr/DeviceProblemCHMMoveError, ntddchgr/DeviceProblemCHMZeroError, ntddchgr/DeviceProblemCalibrationError, ntddchgr/DeviceProblemCartridgeEjectError, ntddchgr/DeviceProblemCartridgeInsertError, ntddchgr/DeviceProblemDoorOpen, ntddchgr/DeviceProblemDriveError, ntddchgr/DeviceProblemGripperError, ntddchgr/DeviceProblemHardware, ntddchgr/DeviceProblemNone, ntddchgr/DeviceProblemPositionError, ntddchgr/DeviceProblemSensorError, ntddchgr/DeviceProblemTargetFailure, ntddchgr/PCHANGER_DEVICE_PROBLEM_TYPE, storage.changer_device_problem_type, structs-changer_907f5212-0009-476e-9187-c9f2edb0f0c8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddchgr.h
req.include-header: 
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
-	ntddchgr.h
api_name:
-	CHANGER_DEVICE_PROBLEM_TYPE
product: Windows
targetos: Windows
req.typenames: CHANGER_DEVICE_PROBLEM_TYPE, *PCHANGER_DEVICE_PROBLEM_TYPE
---

# _CHANGER_DEVICE_PROBLEM_TYPE enumeration


## -description


The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551438">ChangerPerformDiagnostics</a> routine.


## -enum-fields




### -field DeviceProblemNone

Indicates the device has no problem.


### -field DeviceProblemHardware

Indicates the device has had a hardware error.


### -field DeviceProblemCHMError

Indicates the Cartridge Handling Mechanism (CHM) has some problem.


### -field DeviceProblemDoorOpen

Indicates the changer's door is open.


### -field DeviceProblemCalibrationError

Indicates the changer has a calibration problem.


### -field DeviceProblemTargetFailure

Indicates a target failure has occurred.


### -field DeviceProblemCHMMoveError

Indicates the CHM is blocked and cannot move. 


### -field DeviceProblemCHMZeroError

Indicates the CHM could not define zero on one or more of its axis.


### -field DeviceProblemCartridgeInsertError

Indicates an error occurred while loading a cartridge in the drive.


### -field DeviceProblemPositionError

Indicates the CHM has a problem positioning itself to some point.


### -field DeviceProblemSensorError

Indicates the device's sensors are malfunctioning.


### -field DeviceProblemCartridgeEjectError

Indicates an error occurred while unloading a cartridge.


### -field DeviceProblemGripperError

Indicates the media gripper has a problem.


### -field DeviceProblemDriveError

Indicates the changer's drive is malfunctioning.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551438">ChangerPerformDiagnostics</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568029">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_DEVICE_PROBLEM_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

