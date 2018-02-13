---
UID: NF:mcd.ChangerReinitializeUnit
title: ChangerReinitializeUnit function
author: windows-driver-content
description: ChangerReinitializeUnit handles the device-specific aspects of a device-control IRP with the IOCTL code IOCTL_CHANGER_REINITIALIZE_TRANSPORT.
old-location: storage\changerreinitializeunit.htm
old-project: storage
ms.assetid: 161156e3-0da0-458d-b623-67665b2a56c0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ChangerReinitializeUnit function [Storage Devices], ChangerReinitializeUnit, chgrmini_9883d8fd-334e-49f5-93ad-408622aa339f.xml, mcd/ChangerReinitializeUnit, storage.changerreinitializeunit
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
-	ChangerReinitializeUnit
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# ChangerReinitializeUnit function


## -description


<b>ChangerReinitializeUnit</b> handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_reinitialize_transport.md">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. 


## -syntax


````
NTSTATUS ChangerReinitializeUnit(
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



If the changer supports recalibrating a transport element, <b>ChangerReinitializeUnit</b> returns the STATUS_<i>XXX</i> value returned by the system port driver, or one of the following values:
      

STATUS_SUCCESS

STATUS_INVALID_ELEMENT_ADDRESS

STATUS_INVALID_PARAMETER

STATUS_INSUFFICIENT_RESOURCES

If the changer does not support recalibrating a transport element, ChangerReinitializeUnit returns STATUS_INVALID_DEVICE_REQUEST.




## -remarks



This routine is required.

<b>ChangerReinitializeUnit</b> causes the changer to recalibrate its transport element. Depending on the changer, this may return the transport to a "home" position. The changer class driver typically calls <b>ChangerReinitializeUnit</b> after the changer has been powered on or a calling application has initiated a recovery operation. The CHANGER_DEVICE_REINITIALIZE_CAPABLE flag in <b>Features0</b> of <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> indicates whether the changer's transport supports recalibration in those circumstances.

The changer class driver checks the input buffer length in the I/O stack location before calling <b>ChangerReinitializeUnit</b>. <i>Irp</i><b>-&gt;SystemBuffer</b> points to a <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> structure that indicates the element to recalibrate. 

<b>ChangerReinitializeUnit</b> builds an SRB with a CDB to position the transport element and sends it to the system port driver.

<b>ChangerReinitializeUnit</b> sets the <b>Information</b> field in the I/O status block to <b>sizeof</b>(CHANGER_ELEMENT) before returning to the changer class driver.




## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_reinitialize_transport.md">, IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerReinitializeUnit function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

