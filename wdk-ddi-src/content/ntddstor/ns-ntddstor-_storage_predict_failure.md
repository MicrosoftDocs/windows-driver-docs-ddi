---
UID: NS:ntddstor._STORAGE_PREDICT_FAILURE
title: "_STORAGE_PREDICT_FAILURE"
author: windows-driver-content
description: The STORAGE_PREDICT_FAILURE structure is used in conjunction with IOCTL_STORAGE_PREDICT_FAILURE to report whether a device is currently predicting a failure.
old-location: storage\storage_predict_failure.htm
old-project: storage
ms.assetid: 0b88ec6d-a7e0-4bb8-8a12-c7f170ac2334
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTORAGE_PREDICT_FAILURE, PSTORAGE_PREDICT_FAILURE, PSTORAGE_PREDICT_FAILURE structure pointer [Storage Devices], STORAGE_PREDICT_FAILURE, STORAGE_PREDICT_FAILURE structure [Storage Devices], _STORAGE_PREDICT_FAILURE, ntddstor/PSTORAGE_PREDICT_FAILURE, ntddstor/STORAGE_PREDICT_FAILURE, storage.storage_predict_failure, structs-general_b1bed4c9-33a9-4adf-a456-e420d1e2f317.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h, Minitape.h
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
-	ntddstor.h
api_name:
-	STORAGE_PREDICT_FAILURE
product: Windows
targetos: Windows
req.typenames: STORAGE_PREDICT_FAILURE, *PSTORAGE_PREDICT_FAILURE
---

# _STORAGE_PREDICT_FAILURE structure


## -description


The STORAGE_PREDICT_FAILURE structure is used in conjunction with <a href="https://msdn.microsoft.com/library/windows/hardware/ff560587">IOCTL_STORAGE_PREDICT_FAILURE</a> to report whether a device is currently predicting a failure.


## -struct-fields




### -field PredictFailure

Indicates when nonzero that the device is currently predicting an imminent failure.


### -field VendorSpecific

Contains an array that holds 512 bytes of vendor-specific information if the device supports failure prediction. 


## -remarks



Upon receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560587">IOCTL_STORAGE_PREDICT_FAILURE</a> device control request, the disk class driver attempts to verify if an IDE drive supports SMART. If the drive is a SCSI drive, the class driver attempts to verify if the SCSI disk supports the equivalent IDE SMART technology: Information Exception Control Page, X3T10/94-190 Rev 4. 

If the device does not support failure prediction, the disk class driver fails the IRP with a status of STATUS_INVALID_DEVICE_REQUEST.

If the device supports failure prediction, the disk class driver queries the device for failure prediction status. If the device has bad sectors and predicts a failure, the disk class driver returns a nonzero value in <b>PredictFailure</b>. If status indicates that the device does not predict any failures at this time, the disk class driver returns a value of 0 in <b>PredictFailure</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560587">IOCTL_STORAGE_PREDICT_FAILURE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PREDICT_FAILURE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

