---
UID: NF:mcd.ChangerInitializeElementStatus
title: ChangerInitializeElementStatus function
author: windows-driver-content
description: ChangerInitializeElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS.
old-location: storage\changerinitializeelementstatus.htm
old-project: storage
ms.assetid: 1f8f13e0-b0d3-4c94-bd1f-0e42bb75142d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerInitializeElementStatus, ChangerInitializeElementStatus function [Storage Devices], chgrmini_2aa82220-731a-49b0-b3e5-1db93f8e6dc0.xml, mcd/ChangerInitializeElementStatus, storage.changerinitializeelementstatus
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
-	ChangerInitializeElementStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerInitializeElementStatus function


## -description


<b>ChangerInitializeElementStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559409">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



<b>ChangerInitializeElementStatus</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support initializing a range of elements of a particular type and ChangerInitializeElementStatus is called with an element type other than AllElements, it returns STATUS_INVALID_PARAMETER.




## -remarks



This routine is required.

<b>ChangerInitializeElementStatus</b> updates the changer's internal memory with current information about its elements.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerInitializeElementStatus</b>.

<i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551468">CHANGER_INITIALIZE_ELEMENT_STATUS</a> structure as an input parameter that indicates the elements for which to initialize status and whether to initialize element status with data obtained from bar code labels. 

For a SCSI changer, <b>ChangerInitializeElementStatus</b> builds an SRB with a CDB to initialize element status, translates zero-based element addresses to device-specific addresses, and sends the SRB to the system port driver. 

<b>ChangerInitializeElementStatus</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS) before returning to the changer class driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551459">CHANGER_ELEMENT_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551468">CHANGER_INITIALIZE_ELEMENT_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551424">ChangerGetElementStatus</a>
 

 

