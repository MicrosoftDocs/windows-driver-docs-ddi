---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
title: IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL Gets the PnP Container ID of the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_get_containerid.htm
tech.root: audio
ms.assetid: 23B6CB2C-8290-42D7-AA68-6D335ED1818A
ms.date: 5/8/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CONTAINERID, IOCTL_BTHHFP_DEVICE_GET_CONTAINERID control, IOCTL_BTHHFP_DEVICE_GET_CONTAINERID control code [Audio Devices], audio.ioctl_bthhfp_device_get_containerid, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_CONTAINERID</b> 
   IOCTL Gets the PnP Container ID of the Bluetooth device.
<div class="alert"><b>Note</b>  This IOCTL has been deprecated for Windows 8.1, so you should use <a href="https://msdn.microsoft.com/library/windows/hardware/dn265108">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> instead.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

A GUID that is the Container ID.


### -output-buffer-length

The size of a GUID.


### -in-out-buffer








### -inout-buffer-length








### -status-block

N/A


## -remarks



This request completes immediately.

The audio driver stores this container ID in appropriate context data and returns it in the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a> KS property.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265108">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a>
 

 

