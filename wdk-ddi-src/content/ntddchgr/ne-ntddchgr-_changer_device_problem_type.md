---
UID: NE:ntddchgr._CHANGER_DEVICE_PROBLEM_TYPE
title: "_CHANGER_DEVICE_PROBLEM_TYPE"
author: windows-driver-content
description: The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the ChangerPerformDiagnostics routine.
old-location: storage\changer_device_problem_type.htm
old-project: storage
ms.assetid: 2ba267ad-cfd7-4a19-9ecb-16be9187406a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddchgr/DeviceProblemTargetFailure, DeviceProblemNone, ntddchgr/DeviceProblemNone, DeviceProblemCHMZeroError, PCHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/DeviceProblemCHMZeroError, ntddchgr/DeviceProblemCHMError, DeviceProblemPositionError, CHANGER_DEVICE_PROBLEM_TYPE enumeration [Storage Devices], DeviceProblemCHMMoveError, ntddchgr/DeviceProblemCartridgeInsertError, ntddchgr/DeviceProblemGripperError, DeviceProblemTargetFailure, DeviceProblemCalibrationError, CHANGER_DEVICE_PROBLEM_TYPE, DeviceProblemHardware, ntddchgr/CHANGER_DEVICE_PROBLEM_TYPE, DeviceProblemCartridgeEjectError, ntddchgr/DeviceProblemSensorError, DeviceProblemSensorError, ntddchgr/DeviceProblemCartridgeEjectError, ntddchgr/DeviceProblemHardware, DeviceProblemCHMError, DeviceProblemDoorOpen, ntddchgr/DeviceProblemCalibrationError, storage.changer_device_problem_type, structs-changer_907f5212-0009-476e-9187-c9f2edb0f0c8.xml, DeviceProblemCartridgeInsertError, PCHANGER_DEVICE_PROBLEM_TYPE enumeration pointer [Storage Devices], _CHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/DeviceProblemDoorOpen, ntddchgr/PCHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/DeviceProblemDriveError, ntddchgr/DeviceProblemPositionError, *PCHANGER_DEVICE_PROBLEM_TYPE, ntddchgr/DeviceProblemCHMMoveError, DeviceProblemGripperError, DeviceProblemDriveError
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddchgr.h
apiname:
-	CHANGER_DEVICE_PROBLEM_TYPE
product: Windows
targetos: Windows
req.typenames: "*PCHANGER_DEVICE_PROBLEM_TYPE, CHANGER_DEVICE_PROBLEM_TYPE"
---

# _CHANGER_DEVICE_PROBLEM_TYPE enumeration


## -description


The CHANGER_DEVICE_PROBLEM_TYPE data type contains the values returned by the <a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a> routine.


## -syntax


````
typedef enum _CHANGER_DEVICE_PROBLEM_TYPE { 
  DeviceProblemNone                  = 0,
  DeviceProblemHardware              = 1,
  DeviceProblemCHMError              = 2,
  DeviceProblemDoorOpen              = 3,
  DeviceProblemCalibrationError      = 4,
  DeviceProblemTargetFailure         = 5,
  DeviceProblemCHMMoveError          = 6,
  DeviceProblemCHMZeroError          = 7,
  DeviceProblemCartridgeInsertError  = 8,
  DeviceProblemPositionError         = 9,
  DeviceProblemSensorError           = 10,
  DeviceProblemCartridgeEjectError   = 11,
  DeviceProblemGripperError          = 12,
  DeviceProblemDriveError            = 13
} CHANGER_DEVICE_PROBLEM_TYPE, *PCHANGER_DEVICE_PROBLEM_TYPE;
````


## -enum-fields




#### - DeviceProblemNone

Indicates the device has no problem.


#### - DeviceProblemHardware

Indicates the device has had a hardware error.


#### - DeviceProblemCHMError

Indicates the Cartridge Handling Mechanism (CHM) has some problem.


#### - DeviceProblemDoorOpen

Indicates the changer's door is open.


#### - DeviceProblemCalibrationError

Indicates the changer has a calibration problem.


#### - DeviceProblemTargetFailure

Indicates a target failure has occurred.


#### - DeviceProblemCHMMoveError

Indicates the CHM is blocked and cannot move. 


#### - DeviceProblemCHMZeroError

Indicates the CHM could not define zero on one or more of its axis.


#### - DeviceProblemCartridgeInsertError

Indicates an error occurred while loading a cartridge in the drive.


#### - DeviceProblemPositionError

Indicates the CHM has a problem positioning itself to some point.


#### - DeviceProblemSensorError

Indicates the device's sensors are malfunctioning.


#### - DeviceProblemCartridgeEjectError

Indicates an error occurred while unloading a cartridge.


#### - DeviceProblemGripperError

Indicates the media gripper has a problem.


#### - DeviceProblemDriveError

Indicates the changer's drive is malfunctioning.


## -see-also

<a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a>

<a href="..\wmidata\ns-wmidata-_wmi_changer_problem_device_error.md">WMI_CHANGER_PROBLEM_DEVICE_ERROR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_DEVICE_PROBLEM_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

