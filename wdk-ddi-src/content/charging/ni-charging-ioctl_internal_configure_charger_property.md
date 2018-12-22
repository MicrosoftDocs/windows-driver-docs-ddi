---
UID: NI:charging.IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
title: IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
description: The IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control code is sent from a configurable charger to a device that handles configurable chargers. It configures charger properties.
old-location: battery\ioctl_internal_configure_charger_property.htm
tech.root: battery
ms.assetid: B4D10667-29D6-45BF-87CA-D2F59DF78797
ms.date: 02/15/2018
ms.keywords: IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY, IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control, IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control code [Battery Devices], battery.ioctl_internal_configure_charger_property, charging/IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
ms.topic: ioctl
req.header: charging.h
req.include-header: Charging.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 and later operating systems.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	charging.h
api_name:
-	IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY IOCTL


## -description


The <b>IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</b> 
   control code is sent from a configurable charger to a device that handles configurable chargers. It configures charger properties.


## -ioctlparameters




### -input-buffer

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain a structure that starts with a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186644">CONFIGURABLE_CHARGER_PROPERTY_HEADER</a> structure.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186644">CONFIGURABLE_CHARGER_PROPERTY_HEADER</a>
 

 

