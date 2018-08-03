---
UID: NF:mcd.ChangerMoveMedium
title: ChangerMoveMedium function
author: windows-driver-content
description: ChangerMoveMedium handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_MOVE_MEDIUM.
old-location: storage\changermovemedium.htm
tech.root: storage
ms.assetid: 7532c8b5-e77b-4fd0-bac2-78254f6eb9f6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ChangerMoveMedium, ChangerMoveMedium function [Storage Devices], chgrmini_a74d85d9-1b7c-45bc-a826-e60257192a09.xml, mcd/ChangerMoveMedium, storage.changermovemedium
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
-	ChangerMoveMedium
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerMoveMedium function


## -description


<b>ChangerMoveMedium</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://msdn.microsoft.com/library/windows/hardware/ff559410">IOCTL_CHANGER_MOVE_MEDIUM</a>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



<b>ChangerMoveMedium</b> returns the status returned by the system port driver, or one of the following values:
      

STATUS_SUCCESS

STATUS_DESTINATION_ELEMENT_FULL

STATUS_INVALID_ELEMENT_ADDRESS

STATUS_INVALID_DEVICE_REQUEST

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

STATUS_SOURCE_ELEMENT_EMPTY




## -remarks



This routine is required.

<b>ChangerMoveMedium</b> moves a piece of media from one element to another.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerMoveMedium</b>. <i>Irp</i><b>-&gt;SystemBuffer </b>points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551474">CHANGER_MOVE_MEDIUM</a> structure that indicates the transport element, the source, the destination, and whether to flip the medium. 

<b>ChangerMoveMedium</b> first verifies that the transport, source, and destination element addresses are valid and then converts zero-based element addresses to device-specific addresses. It then builds an SRB with a CDB to move the piece of media and sends it to the system port driver.

<b>ChangerMoveMedium</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_MOVE_MEDIUM) before returning to the changer class driver. 




## -see-also




<a href="https://msdn.microsoft.com/4a410f56-cdc1-4cb0-801c-62402caec4ee">,</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551474">CHANGER_MOVE_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551421">ChangerExchangeMedium</a>
 

 

