---
UID: NF:mcd.ChangerGetElementStatus
title: ChangerGetElementStatus function
author: windows-driver-content
description: ChangerGetElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_ELEMENT_STATUS.
old-location: storage\changergetelementstatus.htm
old-project: storage
ms.assetid: 8114d029-fe6e-4466-9e54-5ceadef96949
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ChangerGetElementStatus, ChangerGetElementStatus function [Storage Devices], chgrmini_b0e442c7-18c4-4086-b036-3db43177f6e5.xml, mcd/ChangerGetElementStatus, storage.changergetelementstatus
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
-	ChangerGetElementStatus
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerGetElementStatus function


## -description


<b>ChangerGetElementStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>. 


## -syntax


````
NTSTATUS ChangerGetElementStatus(
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



<b>ChangerGetElementStatus</b> returns the status returned by the system port driver or one of the following values:
      

STATUS_SUCCESS

STATUS_INFO_LENGTH_MISMATCH

STATUS_INSUFFICIENT_RESOURCES

STATUS_INVALID_DEVICE_REQUEST

STATUS_INVALID_ELEMENT_ADDRESS

If VolumeTagInfo is set for a changer that does not support volume tag information, ChangerGetElementStatus returns STATUS_INVALID_PARAMETER.




## -remarks



This routine is required.

<b>ChangerGetElementStatus</b> returns the status and, optionally, volume tag information for all elements in a changer, or the status of a specific number of elements of a particular type.

The changer class driver checks the input and output buffer lengths in the I/O stack location before calling <b>ChangerGetElementStatus</b>.

<i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="..\ntddchgr\ns-ntddchgr-_changer_read_element_status.md">CHANGER_READ_ELEMENT_STATUS</a> structure as an input parameter that indicates the elements for which to report status and whether to report volume tag information. 

<b>ChangerGetElementStatus</b> first builds an SRB with a CDB to read element status command and sends it to the system port driver to retrieve the status of the changer's elements. For most element types, <b>ChangerGetElementStatus</b> then fills in a <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a> structure at <i>Irp</i><b>-&gt;AssociatedIrp.SystemBuffer</b> for each element for which it reports status. However, some elements of type <b>ChangerDrive </b>return product information data. If the device provides product information, the miniclass driver must report the element status data in a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status_ex.md">CHANGER_ELEMENT_STATUS_EX</a> instead of using CHANGER_ELEMENT_STATUS. <b>ChangerGetElementStatus</b> must indicate that product information is present by setting ELEMENT_STATUS_PRODUCT_DATA in the <b>Flags</b> member of the structure.

<b>ChangerGetElementStatus</b> sets the <b>Information</b> field in the I/O status block to the number of bytes returned before returning to the changer class driver. 




## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_list.md">CHANGER_ELEMENT_LIST</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_read_element_status.md">CHANGER_READ_ELEMENT STATUS</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status_ex.md">CHANGER_ELEMENT_STATUS_EX</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_get_element_status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



<a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a>



<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>



<a href="..\mcd\nf-mcd-changergetstatus.md">ChangerGetStatus</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerGetElementStatus function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

