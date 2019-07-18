---
UID: NS:minitape._STORAGE_PREDICT_FAILURE
title: _STORAGE_PREDICT_FAILURE (minitape.h)
description: The STORAGE_PREDICT_FAILURE structure is used in conjunction with IOCTL_STORAGE_PREDICT_FAILURE to report whether a device is currently predicting a failure.
old-location: storage\storage_predict_failure.htm
tech.root: storage
ms.assetid: 0b88ec6d-a7e0-4bb8-8a12-c7f170ac2334
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_PREDICT_FAILURE, PSTORAGE_PREDICT_FAILURE, PSTORAGE_PREDICT_FAILURE structure pointer [Storage Devices], STORAGE_PREDICT_FAILURE, STORAGE_PREDICT_FAILURE structure [Storage Devices], _STORAGE_PREDICT_FAILURE, ntddstor/PSTORAGE_PREDICT_FAILURE, ntddstor/STORAGE_PREDICT_FAILURE, storage.storage_predict_failure, structs-general_b1bed4c9-33a9-4adf-a456-e420d1e2f317.xml"
ms.topic: struct
f1_keywords:
 - "minitape/STORAGE_PREDICT_FAILURE"
req.header: minitape.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddstor.h
api_name:
- STORAGE_PREDICT_FAILURE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_PREDICT_FAILURE, *PSTORAGE_PREDICT_FAILURE
---

# _STORAGE_PREDICT_FAILURE structure


## -description


The STORAGE_PREDICT_FAILURE structure is used in conjunction with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_predict_failure">IOCTL_STORAGE_PREDICT_FAILURE</a> to report whether a device is currently predicting a failure.


## -struct-fields




### -field PredictFailure

Indicates when nonzero that the device is currently predicting an imminent failure.


### -field VendorSpecific

Contains an array that holds 512 bytes of vendor-specific information if the device supports failure prediction. 


## -remarks



Upon receiving an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_predict_failure">IOCTL_STORAGE_PREDICT_FAILURE</a> device control request, the disk class driver attempts to verify if an IDE drive supports SMART. If the drive is a SCSI drive, the class driver attempts to verify if the SCSI disk supports the equivalent IDE SMART technology: Information Exception Control Page, X3T10/94-190 Rev 4. 

If the device does not support failure prediction, the disk class driver fails the IRP with a status of STATUS_INVALID_DEVICE_REQUEST.

If the device supports failure prediction, the disk class driver queries the device for failure prediction status. If the device has bad sectors and predicts a failure, the disk class driver returns a nonzero value in <b>PredictFailure</b>. If status indicates that the device does not predict any failures at this time, the disk class driver returns a value of 0 in <b>PredictFailure</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_predict_failure">IOCTL_STORAGE_PREDICT_FAILURE</a>
 

 

