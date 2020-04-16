---
UID: NF:mcd.ChangerQueryVolumeTags
title: ChangerQueryVolumeTags function (mcd.h)
description: ChangerQueryVolumeTags handles the device-specific aspects of a device-control IRP with the IOCTL code of IOCTL_CHANGER_QUERY_VOLUME_TAGS.
old-location: storage\changerqueryvolumetags.htm
tech.root: storage
ms.assetid: 65579299-829c-48e2-b2f6-dc1a09578e9a
ms.date: 03/29/2018
keywords: ["ChangerQueryVolumeTags function"]
ms.keywords: ChangerQueryVolumeTags, ChangerQueryVolumeTags function [Storage Devices], chgrmini_8d729e15-eade-4300-b640-d5e99f1f5e05.xml, mcd/ChangerQueryVolumeTags, storage.changerqueryvolumetags
f1_keywords:
 - "mcd/ChangerQueryVolumeTags"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mcd.h
api_name:
- ChangerQueryVolumeTags
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerQueryVolumeTags function


## -description


<b>ChangerQueryVolumeTags</b> handles the device-specific aspects of a device-control IRP with the IOCTL code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_query_volume_tags">IOCTL_CHANGER_QUERY_VOLUME_TAGS</a>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



If the changer supports retrieval of volume tag information, <b>ChangerQueryVolumeTags</b> returns the STATUS_<i>XXX</i> value returned by the system port driver, or one of the following values:
      

STATUS_SUCCESS

STATUS_INVALID_ELEMENT_ADDRESS

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support retrieval of volume tag information, ChangerQueryVolumeTags returns STATUS_INVALID_DEVICE_REQUEST.




## -remarks



This routine combines the functionality of two SCSI commands: SEND VOLUME TAGS and REQUEST VOLUME ELEMENT ADDRESS. This routine is required.

<b>ChangerQueryVolumeTags</b> retrieves volume tag information for specified elements. It can also be used to define or clear volume tag information if the changer supports these operations. The CHANGER_VOLUME_IDENTIFICATION flag in the <b>Features0</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure indicates whether the changer supports this functionality.

The changer class driver checks the input and output buffer lengths in the I/O stack location before calling <b>ChangerQueryVolumeTags</b>. <i>Irp</i><b>->SystemBuffer</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a> structure that indicates the elements, the operation to perform, and a template that specifies the volume ID to search for or to set. 

<b>ChangerQueryVolumeTags</b> first checks the action code for unsupported operations, and returns STATUS_INVALID_DEVICE_REQUEST for those it does not support. Next, it builds an SRB with a CDB to indicate the device-specific address of the starting element and sends it to the system port driver, passing the volume ID template as a parameter. (For a SCSI changer, the miniclass driver uses the SCSI command SEND VOLUME TAG.)

If the first SRB succeeds, <b>ChangerQueryVolumeTags</b> builds a second SRB with a CDB to transfer the results of the previous SRB. (For a SCSI changer, the miniclass driver uses the SCSI command REQUEST VOLUME ELEMENT ADDRESS.)

<b>ChangerQueryVolumeTags</b> then fills in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_read_element_address_info">READ_ELEMENT_ADDRESS_INFO</a> structure at <i>Irp</i><b>->AssociatedIrp.SystemBuffer</b> that indicates the number of elements for which volume tag information was transferred, and the information for each element. 

After filling in the system buffer, <b>ChangerQueryVolumeTags</b> sets the <b>Information</b> field in the I/O status block to the number of bytes written to the buffer before returning to the changer class driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">, GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_read_element_address_info">READ_ELEMENT_ADDRESS_INFO</a>
 

 

