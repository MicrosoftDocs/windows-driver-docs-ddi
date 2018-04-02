---
UID: NF:mcd.ChangerGetParameters
title: ChangerGetParameters function
author: windows-driver-content
description: ChangerGetParameters handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_PARAMETERS.
old-location: storage\changergetparameters.htm
old-project: storage
ms.assetid: c1f508a3-6aa8-4fed-af14-6466fcae30da
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerGetParameters, ChangerGetParameters function [Storage Devices], chgrmini_d8cfe74e-46ff-4aee-b1a2-2e55be7ed01f.xml, mcd/ChangerGetParameters, storage.changergetparameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mcd.h
api_name:
-	ChangerGetParameters
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerGetParameters function


## -description


<b>ChangerGetParameters</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



<b>ChangerGetParameters</b> returns the STATUS_<i>XXX</i> value returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INFO_LENGTH_MISMATCH

STATUS_INSUFFICIENT_RESOURCES




## -remarks



This routine is required.

<b>ChangerGetParameters</b> returns the parameters of a changer, including the number and type of its elements and the functionality it supports.

The changer class driver checks the output buffer length in the I/O stack location before calling <b>ChangerGetParameters</b>. If the output buffer length is smaller than <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>) the changer class driver returns with a value of STATUS_INFO_LENGTH_MISMATCH. 

<b>ChangerGetParameters</b> retrieves parameter data from the device by building SRBs with CDBs to get the SCSI parameter header page, the element address page, the transport geometry page, and the device capabilities page, or the non-SCSI equivalent of this data. 

<b>ChangerGetParameters</b> then fills in a GET_CHANGER_PARAMETERS structure at <i>Irp</i><b>-&gt;AssociatedIrp.SystemBuffer</b> before returning to the changer class driver. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559399">IOCTL_CHANGER_GET_PARAMETERS</a>
 

 

