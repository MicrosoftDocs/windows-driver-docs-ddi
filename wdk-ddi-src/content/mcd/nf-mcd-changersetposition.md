---
UID: NF:mcd.ChangerSetPosition
title: ChangerSetPosition function (mcd.h)
description: ChangerSetPosition handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_SET_POSITION.
old-location: storage\changersetposition.htm
tech.root: storage
ms.assetid: cab12c57-dd2b-4453-90ed-7f8954e0fe5d
ms.date: 03/29/2018
keywords: ["ChangerSetPosition function"]
ms.keywords: ChangerSetPosition, ChangerSetPosition function [Storage Devices], chgrmini_28455ca6-3f1f-40ac-a756-c1f026f35f87.xml, mcd/ChangerSetPosition, storage.changersetposition
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
 - ChangerSetPosition
 - mcd/ChangerSetPosition
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mcd.h
api_name:
 - ChangerSetPosition
---

# ChangerSetPosition function


## -description

<b>ChangerSetPosition</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_position">IOCTL_CHANGER_SET_POSITION</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object that represents the changer.

### -param Irp 

[in]
Pointer to the IRP.

## -returns

If the changer supports setting the position of the transport element, <b>ChangerSetPosition</b> returns the status returned by the system port driver, or one of the following values:
      

STATUS_SUCCESS

STATUS_INFO_LENGTH_MISMATCH

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support setting the position of the transport element, ChangerSetPosition returns STATUS_INVALID_DEVICE_REQUEST.

## -remarks

This routine is required.

<b>ChangerSetPosition</b> sets the changer's robotic transport mechanism to the specified destination, typically to optimize moving or exchanging media by first positioning the transport.

The CHANGER_POSITION_TO_ELEMENT flag in <b>Features0</b> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports this functionality.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerSetPosition</b>. <i>Irp</i><b>->SystemBuffer</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_set_position">CHANGER_SET_POSITION</a> structure as an input parameter that indicates the transport element and the destination to set. 

<b>ChangerSetPosition</b> first verifies that the transport and destination element addresses are valid and converts zero-based element addresses to device-specific addresses. It then builds an SRB with a CDB to position the element and sends it to the system port driver.

<b>ChangerSetPosition</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_SET_POSITION) before returning to the changer class driver.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_position">, IOCTL_CHANGER_SET_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_set_position">CHANGER_SET_POSITION</a>

