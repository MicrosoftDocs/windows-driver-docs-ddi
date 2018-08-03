---
UID: NC:ks.PFNKSDEVICESETPOWER
title: PFNKSDEVICESETPOWER
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniDeviceSetPower routine when it receives an IRP_MN_SET_POWER.
old-location: stream\avstrminidevicesetpower.htm
tech.root: stream
ms.assetid: 40d5eb14-b7bd-42b6-a3f5-fe9e8c5c806e
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: AVStrMiniDeviceSetPower, AVStrMiniDeviceSetPower routine [Streaming Media Devices], PFNKSDEVICESETPOWER, avstclbk_8b833d83-a199-44a9-97b8-c4afc624d6d5.xml, ks/AVStrMiniDeviceSetPower, stream.avstrminidevicesetpower
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
-	AVStrMiniDeviceSetPower
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSDEVICESETPOWER callback function


## -description


AVStream calls a minidriver's <i>AVStrMiniDeviceSetPower</i> routine when it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>.


## -parameters




### -param Device [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure that received the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>.


### -param Irp [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> issued by <i>Device</i>.


### -param To [in]

The target device power state.


### -param From [in]

The current device power state.


## -returns



None




## -remarks



If a driver has registered its device for idle detection, the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> to change the power state of an idle device.

The minidriver specifies this routine's address in the <b>SetPower</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is optional.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>
 

 

