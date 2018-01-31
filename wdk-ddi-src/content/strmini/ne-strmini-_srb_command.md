---
UID: NE:strmini._SRB_COMMAND
title: "_SRB_COMMAND"
author: windows-driver-content
description: "."
old-location: stream\srb_command.htm
old-project: stream
ms.assetid: 2A72D3B5-286A-4C20-AFEC-77EDCDD56B6A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SRB_UNKNOWN_STREAM_COMMAND, SRB_UNINITIALIZE_DEVICE, strmini/SRB_PROPOSE_STREAM_RATE, strmini/SRB_GET_DEVICE_PROPERTY, strmini/SRB_STREAM_METHOD, strmini/SRB_OPEN_STREAM, strmini/SRB_SET_DATA_FORMAT, strmini/SRB_SURPRISE_REMOVAL, SRB_CLOSE_STREAM, strmini/SRB_DEVICE_METHOD, strmini/SRB_NOTIFY_IDLE_STATE, strmini/SRB_READ_DATA, strmini/SRB_INDICATE_MASTER_CLOCK, strmini/SRB_BEGIN_FLUSH, strmini/SRB_SET_STREAM_RATE, strmini/SRB_END_FLUSH, SRB_SURPRISE_REMOVAL, SRB_PAGING_OUT_DRIVER, strmini/SRB_CLOSE_MASTER_CLOCK, strmini/SRB_COMMAND, SRB_CHANGE_POWER_STATE, SRB_GET_DATA_INTERSECTION, strmini/SRB_UNINITIALIZE_DEVICE, strmini/SRB_GET_STREAM_PROPERTY, strmini/SRB_OPEN_DEVICE_INSTANCE, SRB_READ_DATA, SRB_COMMAND enumeration [Streaming Media Devices], strmini/SRB_GET_STREAM_INFO, SRB_OPEN_DEVICE_INSTANCE, strmini/SRB_INITIALIZATION_COMPLETE, strmini/SRB_GET_STREAM_STATE, SRB_INDICATE_MASTER_CLOCK, SRB_BEGIN_FLUSH, SRB_STREAM_METHOD, SRB_NOTIFY_IDLE_STATE, SRB_INITIALIZE_DEVICE, strmini/SRB_PAGING_OUT_DRIVER, SRB_SET_STREAM_STATE, SRB_PROPOSE_STREAM_RATE, SRB_INITIALIZATION_COMPLETE, strmini/SRB_OPEN_MASTER_CLOCK, SRB_CLOSE_MASTER_CLOCK, SRB_DEVICE_METHOD, SRB_GET_STREAM_PROPERTY, strmini/SRB_PROPOSE_DATA_FORMAT, SRB_OPEN_MASTER_CLOCK, strmini/SRB_CLOSE_DEVICE_INSTANCE, SRB_SET_DEVICE_PROPERTY, SRB_COMMAND, SRB_WRITE_DATA, SRB_SET_STREAM_PROPERTY, SRB_CLOSE_DEVICE_INSTANCE, SRB_UNKNOWN_DEVICE_COMMAND, SRB_GET_DATA_FORMAT, SRB_GET_STREAM_INFO, SRB_PROPOSE_DATA_FORMAT, strmini/SRB_SET_DEVICE_PROPERTY, stream.srb_command, SRB_GET_STREAM_STATE, _SRB_COMMAND, strmini/SRB_WRITE_DATA, strmini/SRB_UNKNOWN_STREAM_COMMAND, strmini/SRB_INITIALIZE_DEVICE, SRB_SET_DATA_FORMAT, strmini/SRB_CHANGE_POWER_STATE, strmini/SRB_UNKNOWN_DEVICE_COMMAND, strmini/SRB_CLOSE_STREAM, strmini/SRB_SET_STREAM_PROPERTY, strmini/SRB_GET_DATA_INTERSECTION, SRB_OPEN_STREAM, strmini/SRB_SET_STREAM_STATE, strmini/SRB_GET_DATA_FORMAT, SRB_END_FLUSH, SRB_SET_STREAM_RATE, SRB_GET_DEVICE_PROPERTY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
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
-	Strmini.h
apiname:
-	SRB_COMMAND
product: Windows
targetos: Windows
req.typenames: SRB_COMMAND
req.product: Windows 10 or later.
---

# _SRB_COMMAND enumeration


## -description





## -syntax


````
typedef enum _SRB_COMMAND { 
  SRB_READ_DATA,
  SRB_WRITE_DATA,
  SRB_GET_STREAM_STATE,
  SRB_SET_STREAM_STATE,
  SRB_SET_STREAM_PROPERTY,
  SRB_GET_STREAM_PROPERTY,
  SRB_OPEN_MASTER_CLOCK,
  SRB_INDICATE_MASTER_CLOCK,
  SRB_UNKNOWN_STREAM_COMMAND,
  SRB_SET_STREAM_RATE,
  SRB_PROPOSE_DATA_FORMAT,
  SRB_CLOSE_MASTER_CLOCK,
  SRB_PROPOSE_STREAM_RATE,
  SRB_SET_DATA_FORMAT,
  SRB_GET_DATA_FORMAT,
  SRB_BEGIN_FLUSH,
  SRB_END_FLUSH,
  SRB_GET_STREAM_INFO          = 0x100,
  SRB_OPEN_STREAM,
  SRB_CLOSE_STREAM,
  SRB_OPEN_DEVICE_INSTANCE,
  SRB_CLOSE_DEVICE_INSTANCE,
  SRB_GET_DEVICE_PROPERTY,
  SRB_SET_DEVICE_PROPERTY,
  SRB_INITIALIZE_DEVICE,
  SRB_CHANGE_POWER_STATE,
  SRB_UNINITIALIZE_DEVICE,
  SRB_UNKNOWN_DEVICE_COMMAND,
  SRB_PAGING_OUT_DRIVER,
  SRB_GET_DATA_INTERSECTION,
  SRB_INITIALIZATION_COMPLETE,
  SRB_SURPRISE_REMOVAL,
#if (NTDDI_VERSION >= NTDDI_WINXP)
  SRB_DEVICE_METHOD,
  SRB_STREAM_METHOD,
#if ( (NTDDI_VERSION >= NTDDI_WINXPSP2) && (NTDDI_VERSION < NTDDI_WS03) ) || (NTDDI_VERSION >= NTDDI_WS03SP1)


  SRB_NOTIFY_IDLE_STATE
#endif 

#endif } SRB_COMMAND;
````


## -enum-fields




#### - SRB_READ_DATA

Stream-specific code that specifies to read data from hardware.


#### - SRB_WRITE_DATA

Stream-specific code that specifies to write data to the hardware.


#### - SRB_GET_STREAM_STATE

Stream-specific code that specifies to get the state of the stream.


#### - SRB_SET_STREAM_STATE

Stream-specific code that specifies to set the state of the stream.


#### - SRB_SET_STREAM_PROPERTY

Stream-specific code that specifies to set a property of the stream.


#### - SRB_GET_STREAM_PROPERTY

Stream-specific code that specifies to get a property value for the stream.


#### - SRB_OPEN_MASTER_CLOCK

Stream-specific code that indicates that the master clock is on this stream.


#### - SRB_INDICATE_MASTER_CLOCK

Stream-specific code that specifies that the handle is supplied to the master clock.


#### - SRB_UNKNOWN_STREAM_COMMAND

Stream-specific code that specifies that the IRP function is unknown to the class driver.


#### - SRB_SET_STREAM_RATE

Stream-specific code that specifies that the rate is set at which the stream should run.


#### - SRB_PROPOSE_DATA_FORMAT

Stream-specific code that specifies that a new rate is proposed, it does not change the rate.


#### - SRB_CLOSE_MASTER_CLOCK

Stream-specific code that indicates that the master clock is closed.


#### - SRB_PROPOSE_STREAM_RATE

Stream-specific code that indicates a new rate is proposed, it does not change the rate.


#### - SRB_SET_DATA_FORMAT

Stream-specific code that sets a new data format.


#### - SRB_GET_DATA_FORMAT

Stream-specific code that returns the current data format.


#### - SRB_BEGIN_FLUSH

Stream-specific code that begins the flush state.


#### - SRB_END_FLUSH

Stream-specific code that ends the flush state.


#### - SRB_GET_STREAM_INFO

Device instance-specific code that gets the stream information structure.


#### - SRB_OPEN_STREAM

Device instance-specific code that opens the specified stream.


#### - SRB_CLOSE_STREAM

Device instance-specific code that closes the specific stream.


#### - SRB_OPEN_DEVICE_INSTANCE

Device instance-specific code that opens an instance of the device.


#### - SRB_CLOSE_DEVICE_INSTANCE

Device instance-specific code that closes an instance of the device.


#### - SRB_GET_DEVICE_PROPERTY

Device instance-specific code that gets the property of the device.


#### - SRB_SET_DEVICE_PROPERTY

Device instance-specific code that sets the property of the device.


#### - SRB_INITIALIZE_DEVICE

Device instance-specific code that initializes the device.


#### - SRB_CHANGE_POWER_STATE

Device instance-specific code that changes the power state.


#### - SRB_UNINITIALIZE_DEVICE

Device instance-specific code that uninitializes the device.


#### - SRB_UNKNOWN_DEVICE_COMMAND

Device instance-specific code that specifies that the IRP function is unknown to the class driver.


#### - SRB_PAGING_OUT_DRIVER

Device instance-specific code that indicates that the driver is to be paged out only if it is enabled in the registry. Board ints should be disabled and STATUS_SUCCESS returned.


#### - SRB_GET_DATA_INTERSECTION

Device instance-specific code that returns stream data intersection.


#### - SRB_INITIALIZATION_COMPLETE

Device instance-specific code that indicates that the initialization sequence has completed.


#### - SRB_SURPRISE_REMOVAL

Device instance-specific code that indicates a surprise removal of hardware has occurred.


#### - SRB_DEVICE_METHOD



#### - SRB_STREAM_METHOD



#### - SRB_NOTIFY_IDLE_STATE

Device instance-specific code that specifies to call on first open and last close.

