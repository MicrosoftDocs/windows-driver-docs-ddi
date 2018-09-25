---
UID: NI:ks.IOCTL_KS_RESET_STATE
title: IOCTL_KS_RESET_STATE
author: windows-driver-content
description: An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at Acquire-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_reset_state.htm
tech.root: stream
ms.assetid: 0f3fd5ae-f8ce-4a2f-b8c0-4ac101569e09
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IOCTL_KS_RESET_STATE, IOCTL_KS_RESET_STATE control, IOCTL_KS_RESET_STATE control code [Streaming Media Devices], ks-ioctl_ce7c174b-952d-4b08-ab05-f8843155af33.xml, ks/IOCTL_KS_RESET_STATE, stream.ioctl_ks_reset_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	IOCTL_KS_RESET_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_RESET_STATE IOCTL


## -description


An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at <i>Acquire</i>-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567142">KsSynchronousDeviceControl</a> function.


## -ioctlparameters




### -input-buffer

A client provides a buffer that contains the reset value (KSRESET_BEGIN, KSRESET_END) in the <b>InBuffer</b> parameter. 


### -input-buffer-length

<b>InLength</b> specifies size, in bytes, of the input buffer contents.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks



Initiate a reset on a pin by sending IOCTL_KS_RESET_STATE with a value of KSRESET_BEGIN in the InBuffer parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567142">KsSynchronousDeviceControl</a>. 

When the reset state is initiated, existing read and write requests are canceled. While in the reset state, any new read or write requests are rejected with STATUS_DEVICE_NOT_READY.

To terminate the reset state, send IOCTL_KS_RESET_STATE with a value of KSRESET_END.

Note that the reset state is not canceled by changing the pin state.

When the reset state is terminated, the pin can again accept new data and pass data to other connections.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556317">AVStrMiniFilterReset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556354">AVStrMiniPinReset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560923">KsAcquireResetValue</a>
 

 

