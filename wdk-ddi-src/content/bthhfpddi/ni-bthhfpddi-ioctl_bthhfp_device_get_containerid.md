---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
title: IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL Gets the PnP Container ID of the Bluetooth device.
old-location: audio\ioctl_bthhfp_device_get_containerid.htm
old-project: audio
ms.assetid: 23B6CB2C-8290-42D7-AA68-6D335ED1818A
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_CONTAINERID, IOCTL_BTHHFP_DEVICE_GET_CONTAINERID control code [Audio Devices], audio.ioctl_bthhfp_device_get_containerid, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthhfpddi.h
apiname:
-	IOCTL_BTHHFP_DEVICE_GET_CONTAINERID
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_CONTAINERID IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_CONTAINERID</b> 
   IOCTL Gets the PnP Container ID of the Bluetooth device.
<div class="alert"><b>Note</b>  This IOCTL has been deprecated for Windows 8.1, so you should use <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> instead.</div><div> </div>

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



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

N/A


## -remarks



This request completes immediately.

The audio driver stores this container ID in appropriate context data and returns it in the driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a> KS property.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_CONTAINERID control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

