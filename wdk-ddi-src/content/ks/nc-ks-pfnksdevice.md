---
UID: NC:ks.PFNKSDEVICE
title: PFNKSDEVICE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDevicePostStart routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start.
old-location: stream\avstrminidevicepoststart.htm
old-project: stream
ms.assetid: 5a08cdb2-f4e5-4c32-b98e-e854412954e9
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: AVStrMiniDevicePostStart, AVStrMiniDevicePostStart routine [Streaming Media Devices], PFNKSDEVICE, avstclbk_2eb05ad1-c345-4625-9f76-f979e3ea7962.xml, ks/AVStrMiniDevicePostStart, stream.avstrminidevicepoststart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
-	ks.h
api_name:
-	AVStrMiniDevicePostStart
product: Windows
targetos: Windows
req.typenames: 
---

# PFNKSDEVICE callback function


## -description


An AVStream minidriver's <i>AVStrMiniDevicePostStart</i> routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start.


## -parameters




### -param Device [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure describing the device for which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request was sent.


## -returns



Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If this routine returns failure, any pending <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> requests between the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> request will be failed. Do not return STATUS_PENDING.




## -remarks



The minidriver specifies this routine's address in the <b>PostStart</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is optional.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>
 

 

