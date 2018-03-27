---
UID: NC:irb.IDE_HW_INITIALIZE
title: IDE_HW_INITIALIZE
author: windows-driver-content
description: The IdeHwInitialize miniport driver routine configures the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwinitialize.htm
old-project: storage
ms.assetid: 5665ff0a-3cbf-4ac5-adf7-5b383bac5117
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDE_HW_INITIALIZE, IdeHwInitialize, IdeHwInitialize routine [Storage Devices], atartns_dcb52bc9-05c9-436f-a2b2-f9c1b68d1d33.xml, irb/IdeHwInitialize, storage.idehwinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: irb.h
req.include-header: Irb.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	irb.h
api_name:
-	IdeHwInitialize
product: Windows
targetos: Windows
req.typenames: IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS, IDD_DRIVER_GLOBALS, *PIDD_DRIVER_GLOBALS
---

# IDE_HW_INITIALIZE callback


## -description


The <b><i>IdeHwInitialize</i></b> miniport driver routine configures the indicated device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the miniport driver per channel device extension.


### -param DeviceParameters [in, out]

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a> that identifies the device to configure and the device parameters with which to configure the device.


### -param IdentifyData [in]

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559006">IDENTIFY_DEVICE_DATA</a> that contains the identify data that is returned by the device.


## -returns



<b><i>IdeHwInitialize</i></b> returns <b>TRUE</b> if the operation succeeds. It returns <b>FALSE</b> if the operation fails. 




## -remarks



After the miniport driver enumerates the devices on a channel, it calls the <b><i>IdeHwInitialize</i></b> routine one time for each device it enumerates. The <b><i>IdeHwInitialize</i></b> routine must configure each device based on the information that is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a> structure, pointed to by the <i>DeviceParameters</i> parameter. In exceptional cases, the miniport driver can configure the device by using a set of parameters that differ from those contained in <b>IDE_DEVICE_PARAMETERS</b>. In such cases, the miniport driver must update the information in <b>IDE_DEVICE_PARAMETERS</b> to contain the parameter value that it actually used to configure the device. After the <b><i>IdeHwInitialize</i></b> routine returns, the port driver updates its cached information with the parameter values that are provided by the miniport driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559006">IDENTIFY_DEVICE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559090">IDE_DEVICE_PARAMETERS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IdeHwInitialize routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

