---
UID: NF:strmini.StreamClassReadWriteConfig
title: StreamClassReadWriteConfig function (strmini.h)
description: The StreamClassReadWriteConfig routine reads or writes configuration data for the minidriver's parent bus driver.
old-location: stream\streamclassreadwriteconfig.htm
tech.root: stream
ms.assetid: ae8c1478-b429-4af1-a36d-96145696a990
ms.date: 04/23/2018
ms.keywords: StreamClassReadWriteConfig, StreamClassReadWriteConfig routine [Streaming Media Devices], strclass-routines_5bfa9287-1b6a-40d8-abdc-637fe88e6372.xml, stream.streamclassreadwriteconfig, strmini/StreamClassReadWriteConfig
ms.topic: function
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassReadWriteConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassReadWriteConfig function


## -description


The <b>StreamClassReadWriteConfig</b> routine reads or writes configuration data for the minidriver's parent bus driver.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559682">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559702">HW_STREAM_REQUEST_BLOCK</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559697">HW_STREAM_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff559706">HW_TIME_CONTEXT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param Read [in]

Specifies whether to read or write the configuration information. A value of <b>TRUE</b> indicates that a read is requested. A value of <b>FALSE</b> indicates that a write should be performed.


### -param Buffer [in, out]

Points to the buffer to use to read/write the configuration information.


### -param Offset [in]

Specifies the offset within the configuration information to begin the read/write operation.


### -param Length [in]

Specifies the length of the data to read or write.


## -returns



Returns <b>TRUE</b> on success, <b>FALSE</b> on failure.




## -remarks



This routine reads or writes configuration information for the minidriver's parent bus driver. For example, for a PCI device, <b>StreamClassReadWriteConfig</b> reads or writes PCI configuration information.

This routine can only be called at PASSIVE_LEVEL.



