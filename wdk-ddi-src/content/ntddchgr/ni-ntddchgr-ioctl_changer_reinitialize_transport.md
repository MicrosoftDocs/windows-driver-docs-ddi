---
UID: NI:ntddchgr.IOCTL_CHANGER_REINITIALIZE_TRANSPORT
title: IOCTL_CHANGER_REINITIALIZE_TRANSPORT
author: windows-driver-content
description: Physically recalibrates a transport element, typically after the changer has been powered on or a calling application has initiated a recovery operation. Recalibration may involve returning the transport to its &#0034;home&#0034; position.
old-location: storage\ioctl_changer_reinitialize_transport.htm
old-project: storage
ms.assetid: 35b40514-a7a6-4860-a633-fe273ef21ba2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CHANGER_REINITIALIZE_TRANSPORT, IOCTL_CHANGER_REINITIALIZE_TRANSPORT control code [Storage Devices], k307_36f3bd40-f084-4b11-b2e1-5e4ff976ba64.xml, ntddchgr/IOCTL_CHANGER_REINITIALIZE_TRANSPORT, storage.ioctl_changer_reinitialize_transport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_REINITIALIZE_TRANSPORT
product:
- Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_REINITIALIZE_TRANSPORT IOCTL


## -description


Physically recalibrates a transport element, typically after the changer has been powered on or a calling application has initiated a recovery operation. Recalibration may involve returning the transport to its "home" position.


## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> indicates the element to initialize. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a>). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_ELEMENT). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a>
 

 

