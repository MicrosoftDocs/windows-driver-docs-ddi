---
UID: NF:strmini.StreamClassRegisterAdapter
title: StreamClassRegisterAdapter function (strmini.h)
description: The StreamClassRegisterAdapter routine registers a stream class minidriver.The name StreamClassRegisterAdapter is supported for backward compatibility only.Instead, Microsoft recommends the use of StreamClassRegisterMinidriver, an alias of StreamClassRegisterAdapter. The name StreamClassRegisterMinidriver more accurately indicates that the routine registers a stream class minidriver. Once registered, a minidriver can drive any number of adapter instances in a system.The StreamClassRegisterMinidriver routine registers a stream minidriver with the stream class driver.
old-location: stream\streamclassregisterminidriver.htm
tech.root: stream
ms.assetid: 231a0e11-2968-4a51-9a51-ae98a483f85b
ms.date: 04/23/2018
keywords: ["StreamClassRegisterAdapter function"]
ms.keywords: StreamClassRegisterAdapter, StreamClassRegisterAdapter function [Streaming Media Devices], StreamClassRegisterMinidriver, strclass-routines_5336cc3e-8abd-4943-a191-12dbf9d25b85.xml, stream.streamclassregisterminidriver, strmini/StreamClassRegisterAdapter
f1_keywords:
 - "strmini/StreamClassRegisterAdapter"
 - "StreamClassRegisterAdapter"
req.header: strmini.h
req.include-header: Strmini.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- strmini.h
api_name:
- StreamClassRegisterAdapter
targetos: Windows
req.typenames: 
---

# StreamClassRegisterAdapter function


## -description


The <b>StreamClassRegisterAdapter</b> routine registers a stream class minidriver.

The name <b>StreamClassRegisterAdapter</b> is supported for backward compatibility only.

Instead, Microsoft recommends the use of <b>StreamClassRegisterMinidriver</b>, an alias of <b>StreamClassRegisterAdapter</b>. The name <b>StreamClassRegisterMinidriver</b> more accurately indicates that the routine registers a stream class minidriver. Once registered, a minidriver can drive any number of adapter instances in a system.

The <b>StreamClassRegisterMinidriver</b> routine registers a stream minidriver with the stream class driver.


## -parameters




### -param Argument1 
[in]
Points to the first argument to the minidriver's <b>DriverEntry</b> routine.


### -param Argument2 
[in]
Points to the second argument to the minidriver's <b>DriverEntry</b> routine.


### -param HwInitializationData 
[in]
Points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure that provides the information the class driver needs to begin initializing the minidriver.


## -returns



Returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -remarks



A stream minidriver must call <b>StreamClassRegisterMinidriver</b> within its <b>DriverEntry</b> routine. 

The stream minidriver's <b>DriverEntry</b> initializes a stream class minidriver. This routine is required.

Argument1 Supplies a context value with which the adapter minidriver should call <b>StreamClassRegisterMinidriver</b>. For Windows 2000 and later, this points to a DRIVER_OBJECT.

Argument2 Supplies a second context value with which the adapter minidriver should call <b>StreamClassRegisterMinidriver</b>. For Windows 2000 and later, this points to a registry path.

<b>DriverEntry</b> returns the value returned by its call to <b>StreamClassRegisterMinidriver</b>.

Remarks
<b>DriverEntry</b> is the initial entry point for a stream class minidriver.

Since <b>StreamClassRegisterMinidriver</b> performs most of the required driver initialization, the primary task of a stream class minidriver's DriverEntry routine is to allocate and fill in a HW_INITIALIZATION_DATA structure with driver-specific constants and entry points. The DriverEntry should then call <b>StreamClassRegisterMinidriver</b>.



Most of the information passed in the HW_INITIALIZATION_DATA structure informs the class driver of the minidriver-wide callbacks, and what size buffers to allocate for the minidriver's data structures. The class driver queries the minidriver for additional start-up information through <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-initialize-device">SRB_INITIALIZE_DEVICE</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-stream-info">SRB_GET_STREAM_INFO</a> requests to the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a> routine (passed as the <b>HwReceivePacket</b> member of HW_INITIALIZATION_DATA).

Once registered, a minidriver can drive any number of adapter instances in a system.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-stream-info">SRB_GET_STREAM_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-initialize-device">SRB_INITIALIZE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a>
 

 

