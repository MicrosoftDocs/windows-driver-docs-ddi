---
UID: NF:mcd.ChangerSetAccess
title: ChangerSetAccess function
author: windows-driver-content
description: ChangerSetAccess handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_ACCESS.
old-location: storage\changersetaccess.htm
old-project: storage
ms.assetid: 586820c5-5662-4f2d-9413-d06b9794173a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerSetAccess, ChangerSetAccess function [Storage Devices], chgrmini_3b7a1ae3-1724-464a-942a-54ecbae6329d.xml, mcd/ChangerSetAccess, storage.changersetaccess
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
req.lib: NtosKrnl.exe
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
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerSetAccess function


## -description


<b>ChangerSetAccess</b> handles the device-specific aspects of a device-control IRP with the IOCTL code<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md"> IOCTL_CHANGER_SET_ACCESS</a>. 


## -syntax


````
NTSTATUS ChangerSetAccess(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````


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

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerSetAccess</b>. <i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="..\ntddchgr\ns-ntddchgr-_changer_set_access.md">CHANGER_SET_ACCESS</a> structure as an input parameter that indicates the element to set and the operation to perform.

<b>ChangerSetAccess</b> first checks for unsupported elements and operations, and returns the appropriate status code for those it doesn't support.

Next, <b>ChangerSetAccess</b> translates the zero-based element address passed by the system to the device-specific element address required by the changer.

Finally, <b>ChangerSetAccess</b> builds an SRB with a CDB for the given operation on the given element and sends it to the system port driver. The command to use depends on the changer. For example, the Exabyte miniclass driver uses the SCSI command PREVENT ALLOW MEDIUM REMOVAL to lock or unlock a changer door and MOVE MEDIUM to extend or retract an IEport.




## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_changer_set_access.md">CHANGER_SET_ACCESS</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_set_access.md">IOCTL_CHANGER_SET_ACCESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerSetAccess function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

