---
UID: NF:mcd.ChangerMoveMedium
title: ChangerMoveMedium function
author: windows-driver-content
description: ChangerMoveMedium handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_MOVE_MEDIUM.
old-location: storage\changermovemedium.htm
old-project: storage
ms.assetid: 7532c8b5-e77b-4fd0-bac2-78254f6eb9f6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ChangerMoveMedium, storage.changermovemedium, chgrmini_a74d85d9-1b7c-45bc-a826-e60257192a09.xml, mcd/ChangerMoveMedium, ChangerMoveMedium function [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mcd.h
apiname:
-	ChangerMoveMedium
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerMoveMedium function


## -description


<b>ChangerMoveMedium</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>. 


## -syntax


````
NTSTATUS ChangerMoveMedium(
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

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerMoveMedium</b>. <i>Irp</i><b>-&gt;SystemBuffer </b>points to a <a href="..\ntddchgr\ns-ntddchgr-_changer_move_medium.md">CHANGER_MOVE_MEDIUM</a> structure that indicates the transport element, the source, the destination, and whether to flip the medium. 

<b>ChangerMoveMedium</b> first verifies that the transport, source, and destination element addresses are valid and then converts zero-based element addresses to device-specific addresses. It then builds an SRB with a CDB to move the piece of media and sends it to the system port driver.

<b>ChangerMoveMedium</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_MOVE_MEDIUM) before returning to the changer class driver. 




## -see-also

<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_move_medium.md">CHANGER_MOVE_MEDIUM</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">,</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerMoveMedium function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

