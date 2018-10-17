---
UID: NF:mcd.ChangerSetAccess
title: ChangerSetAccess function
author: windows-driver-content
description: ChangerSetAccess handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_ACCESS.
old-location: storage\changersetaccess.htm
tech.root: storage
ms.assetid: 586820c5-5662-4f2d-9413-d06b9794173a
ms.date: 3/29/2018
ms.keywords: ChangerSetAccess, ChangerSetAccess function [Storage Devices], chgrmini_3b7a1ae3-1724-464a-942a-54ecbae6329d.xml, mcd/ChangerSetAccess, storage.changersetaccess
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
-	ChangerSetAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerSetAccess function


## -description


<b>ChangerSetAccess</b> handles the device-specific aspects of a device-control IRP with the IOCTL code<a href="https://msdn.microsoft.com/8927e862-94e4-45ce-9245-5c6f5629fc01"> IOCTL_CHANGER_SET_ACCESS</a>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



If the changer supports setting access, <b>ChangerSetAccess</b> returns the STATUS_<i>XXX </i>value returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INSUFFICIENT_RESOURCES

STATUS_INVALID_PARAMETER

If the changer does not support setting access, ChangerSetAccess returns STATUS_INVALID_DEVICE_REQUEST.




## -remarks



This routine is required.

<b>ChangerSetAccess</b> locks or unlocks a changer's IEport, door, or keypad, and extends or retracts an IEport.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerSetAccess</b>. <i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551481">CHANGER_SET_ACCESS</a> structure as an input parameter that indicates the element to set and the operation to perform.

<b>ChangerSetAccess</b> first checks for unsupported elements and operations, and returns the appropriate status code for those it doesn't support.

Next, <b>ChangerSetAccess</b> translates the zero-based element address passed by the system to the device-specific element address required by the changer.

Finally, <b>ChangerSetAccess</b> builds an SRB with a CDB for the given operation on the given element and sends it to the system port driver. The command to use depends on the changer. For example, the Exabyte miniclass driver uses the SCSI command PREVENT ALLOW MEDIUM REMOVAL to lock or unlock a changer door and MOVE MEDIUM to extend or retract an IEport.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551481">CHANGER_SET_ACCESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559422">IOCTL_CHANGER_SET_ACCESS</a>
 

 

