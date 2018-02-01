---
UID: NI:ks.IOCTL_KS_RESET_STATE
title: IOCTL_KS_RESET_STATE
author: windows-driver-content
description: An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at Acquire-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_reset_state.htm
old-project: stream
ms.assetid: 0f3fd5ae-f8ce-4a2f-b8c0-4ac101569e09
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_ks_reset_state, IOCTL_KS_RESET_STATE control code [Streaming Media Devices], IOCTL_KS_RESET_STATE, ks/IOCTL_KS_RESET_STATE, ks-ioctl_ce7c174b-952d-4b08-ab05-f8843155af33.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	IOCTL_KS_RESET_STATE
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_RESET_STATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at <i>Acquire</i>-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> function.


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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks


Initiate a reset on a pin by sending IOCTL_KS_RESET_STATE with a value of KSRESET_BEGIN in the InBuffer parameter of <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a>. 

When the reset state is initiated, existing read and write requests are canceled. While in the reset state, any new read or write requests are rejected with STATUS_DEVICE_NOT_READY.

To terminate the reset state, send IOCTL_KS_RESET_STATE with a value of KSRESET_END.

Note that the reset state is not canceled by changing the pin state.

When the reset state is terminated, the pin can again accept new data and pass data to other connections.



## -see-also

<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556354">AVStrMiniPinReset</a>

<a href="..\ks\nc-ks-pfnksfiltervoid.md">AVStrMiniFilterReset</a>

<a href="..\ks\nf-ks-ksacquireresetvalue.md">KsAcquireResetValue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_RESET_STATE control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

