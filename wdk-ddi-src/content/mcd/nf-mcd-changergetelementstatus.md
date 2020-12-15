---
UID: NF:mcd.ChangerGetElementStatus
title: ChangerGetElementStatus function (mcd.h)
description: ChangerGetElementStatus handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_GET_ELEMENT_STATUS.
old-location: storage\changergetelementstatus.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ChangerGetElementStatus function"]
ms.keywords: ChangerGetElementStatus, ChangerGetElementStatus function [Storage Devices], chgrmini_b0e442c7-18c4-4086-b036-3db43177f6e5.xml, mcd/ChangerGetElementStatus, storage.changergetelementstatus
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ChangerGetElementStatus
 - mcd/ChangerGetElementStatus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mcd.h
api_name:
 - ChangerGetElementStatus
---

# ChangerGetElementStatus function


## -description

<b>ChangerGetElementStatus</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object that represents the changer.

### -param Irp 

[in]
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

<i>Irp</i><b>->SystemBuffer</b> points to a <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_read_element_status">CHANGER_READ_ELEMENT_STATUS</a> structure as an input parameter that indicates the elements for which to report status and whether to report volume tag information. 

<b>ChangerGetElementStatus</b> first builds an SRB with a CDB to read element status command and sends it to the system port driver to retrieve the status of the changer's elements. For most element types, <b>ChangerGetElementStatus</b> then fills in a <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a> structure at <i>Irp</i><b>->AssociatedIrp.SystemBuffer</b> for each element for which it reports status. However, some elements of type <b>ChangerDrive </b>return product information data. If the device provides product information, the miniclass driver must report the element status data in a structure of type <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status_ex">CHANGER_ELEMENT_STATUS_EX</a> instead of using CHANGER_ELEMENT_STATUS. <b>ChangerGetElementStatus</b> must indicate that product information is present by setting ELEMENT_STATUS_PRODUCT_DATA in the <b>Flags</b> member of the structure.

<b>ChangerGetElementStatus</b> sets the <b>Information</b> field in the I/O status block to the number of bytes returned before returning to the changer class driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_list">CHANGER_ELEMENT_LIST</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status_ex">CHANGER_ELEMENT_STATUS_EX</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_read_element_status">CHANGER_READ_ELEMENT STATUS</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetstatus">ChangerGetStatus</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitializeelementstatus">ChangerInitializeElementStatus</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>
