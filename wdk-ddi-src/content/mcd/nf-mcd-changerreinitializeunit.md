---
UID: NF:mcd.ChangerReinitializeUnit
title: ChangerReinitializeUnit function (mcd.h)
description: ChangerReinitializeUnit handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_REINITIALIZE_TRANSPORT.
old-location: storage\changerreinitializeunit.htm
tech.root: storage
ms.assetid: 161156e3-0da0-458d-b623-67665b2a56c0
ms.date: 03/29/2018
ms.keywords: ChangerReinitializeUnit, ChangerReinitializeUnit function [Storage Devices], chgrmini_9883d8fd-334e-49f5-93ad-408622aa339f.xml, mcd/ChangerReinitializeUnit, storage.changerreinitializeunit
ms.topic: function
f1_keywords:
 - "mcd/ChangerReinitializeUnit"
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
- ChangerReinitializeUnit
product:
- Windows
targetos: Windows
req.typenames: 
---

# ChangerReinitializeUnit function


## -description


<b>ChangerReinitializeUnit</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_reinitialize_transport">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object that represents the changer. 


### -param Irp [in]

Pointer to the IRP. 


## -returns



If the changer supports recalibrating a transport element, <b>ChangerReinitializeUnit</b> returns the STATUS_<i>XXX</i> value returned by the system port driver, or one of the following values:
      

STATUS_SUCCESS

STATUS_INVALID_ELEMENT_ADDRESS

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support recalibrating a transport element, ChangerReinitializeUnit returns STATUS_INVALID_DEVICE_REQUEST.




## -remarks



This routine is required.

<b>ChangerReinitializeUnit</b> causes the changer to recalibrate its transport element. Depending on the changer, this may return the transport to a "home" position. The changer class driver typically calls <b>ChangerReinitializeUnit</b> after the changer has been powered on or a calling application has initiated a recovery operation. The CHANGER_DEVICE_REINITIALIZE_CAPABLE flag in <b>Features0</b> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> indicates whether the changer's transport supports recalibration in those circumstances.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerReinitializeUnit</b>. <i>Irp</i><b>->SystemBuffer</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a> structure that indicates the element to recalibrate. 

<b>ChangerReinitializeUnit</b> builds an SRB with a CDB to position the transport element and sends it to the system port driver.

<b>ChangerReinitializeUnit</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_ELEMENT) before returning to the changer class driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_reinitialize_transport">, IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>
 

 

