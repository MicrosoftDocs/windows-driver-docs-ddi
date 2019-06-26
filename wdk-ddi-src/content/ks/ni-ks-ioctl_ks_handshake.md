---
UID: NI:ks.IOCTL_KS_HANDSHAKE
title: IOCTL_KS_HANDSHAKE (ks.h)
description: A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins.
old-location: stream\ioctl_ks_handshake.htm
tech.root: stream
ms.assetid: 63c50af0-365b-4074-a703-9e43b1514a55
ms.date: 04/23/2018
ms.keywords: IOCTL_KS_HANDSHAKE, IOCTL_KS_HANDSHAKE control, IOCTL_KS_HANDSHAKE control code [Streaming Media Devices], ks-ioctl_f848d65c-b795-439e-a8a1-d4c2e0764ef1.xml, ks/IOCTL_KS_HANDSHAKE, stream.ioctl_ks_handshake
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- IOCTL_KS_HANDSHAKE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_HANDSHAKE IOCTL


## -description



A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. The client calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> with IOCTL_KS_HANDSHAKE and the parameters described below.

To attempt a protocol handshake with a pin that is already connected, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinhandshake">KsPinHandshake</a>.




## -ioctlparameters




### -input-buffer

The client places a pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kshandshake">KSHANDSHAKE</a> in the <b>InBuffer</b> parameter. 


### -input-buffer-length

<b>InLength </b>must be equal to sizeof(KSHANDSHAKE).


### -output-buffer

The client places a pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kshandshake">KSHANDSHAKE</a> in the <b>OutBuffer</b> parameter. If the request is successful, handshake information is placed in this location.


### -output-buffer-length

<b>OutLength </b>must be equal to sizeof(KSHANDSHAKE).


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, IoStatus.Information is set to sizeof(KSHANDSHAKE).

This IOCTL can be sent from kernel-mode only. If the request is sent from user mode, the Status member is set to STATUS_INVALID_DEVICE_REQUEST. 

If the <b>InLength</b> and <b>OutLength</b> parameters in the call to <b>KsSynchronousDeviceControl</b> are not both equal to sizeof(KSHANDSHAKE), the Status member is set to STATUS_INVALID_BUFFER_SIZE.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinhandshake">AVStrMiniPinHandshake</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kshandshake">KSHANDSHAKE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinhandshake">KsPinHandshake</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinregisterhandshakecallback">KsPinRegisterHandshakeCallback</a>
 

 

