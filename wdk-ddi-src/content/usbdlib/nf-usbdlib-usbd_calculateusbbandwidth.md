---
UID: NF:usbdlib.USBD_CalculateUsbBandwidth
title: USBD_CalculateUsbBandwidth function
author: windows-driver-content
description: The USBD_CalculateUsbBandwidth routine has been deprecated in Windows XP and later operating systems. Do not use.
old-location: buses\usbd_calculateusbbandwidth.htm
old-project: usbref
ms.assetid: a54f3fb4-032a-4538-8b6d-20d6834d08c4
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: USBD_CalculateUsbBandwidth, USBD_CalculateUsbBandwidth routine [Buses], buses.usbd_calculateusbbandwidth, usbdlib/USBD_CalculateUsbBandwidth, usbfunc_a422b001-17f1-42b4-b10e-3d64d4279530.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
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
req.lib: Usbd.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_CalculateUsbBandwidth
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_CalculateUsbBandwidth function


## -description


The <b>USBD_CalculateUsbBandwidth</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 


## -parameters




### -param MaxPacketSize [in]

Specifies the maximum packet size. 


### -param EndpointType [in]

Contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff539119">USBD_PIPE_TYPE</a> that specifies the pipe type.


### -param LowSpeed [in]

Indicates, when <b>TRUE</b>, that the device is a low speed device. When <b>FALSE</b>, this member indicates that the device is a hi-speed device. 


## -returns



The <b>USBD_CalculateUsbBandwidth</b> routine returns zero for bulk and control endpoints and the bandwidth consumed in bits per millisecond. returns for all other endpoints. 




## -remarks



The <b>USBD_CalculateUsbBandwidth</b> routine approximates the bandwidth using the following procedure. First, <b>USBD_CalculateUsbBandwidth</b> adds the largest possible packet size, specified in <i>MaxPacketSize</i>, to the overhead associated with the type of end point specified in <i>EndpointType</i>. Next, <b>USBD_CalculateUsbBandwidth</b> multiplies this sum by 8 to convert the units from <i>bytes</i> per millisecond into <i>bits</i> per millisecond. Finally, <b>USBD_CalculateUsbBandwidth</b> multiplies this quantity by 7/6 to account for filler bits. In a worst case scenario, there will be one bit of filler data stuffed into the data stream for every six bits of data. <b>USBD_CalculateUsbBandwidth</b> uses worst-case assumptions to calculate the bandwidth required by the pipe. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539119">USBD_PIPE_TYPE</a>
 

 

