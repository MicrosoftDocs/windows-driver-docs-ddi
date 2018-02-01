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
ms.keywords: SRB_COMMAND, strmini/SRB_SET_STREAM_PROPERTY, strmini/SRB_READ_DATA, SRB_OPEN_MASTER_CLOCK, SRB_STREAM_METHOD, SRB_CLOSE_STREAM, strmini/SRB_INDICATE_MASTER_CLOCK, SRB_SET_STREAM_STATE, strmini/SRB_UNKNOWN_STREAM_COMMAND, strmini/SRB_DEVICE_METHOD, SRB_PROPOSE_DATA_FORMAT, strmini/SRB_SET_DEVICE_PROPERTY, strmini/SRB_WRITE_DATA, strmini/SRB_GET_STREAM_INFO, strmini/SRB_INITIALIZE_DEVICE, strmini/SRB_CLOSE_STREAM, strmini/SRB_UNKNOWN_DEVICE_COMMAND, SRB_OPEN_STREAM, SRB_GET_STREAM_STATE, strmini/SRB_INITIALIZATION_COMPLETE, SRB_COMMAND enumeration [Streaming Media Devices], strmini/SRB_CLOSE_MASTER_CLOCK, strmini/SRB_END_FLUSH, SRB_GET_DEVICE_PROPERTY, SRB_BEGIN_FLUSH, strmini/SRB_SET_STREAM_STATE, SRB_CHANGE_POWER_STATE, SRB_DEVICE_METHOD, strmini/SRB_OPEN_DEVICE_INSTANCE, SRB_CLOSE_MASTER_CLOCK, SRB_UNINITIALIZE_DEVICE, SRB_PAGING_OUT_DRIVER, strmini/SRB_OPEN_STREAM, SRB_NOTIFY_IDLE_STATE, SRB_GET_DATA_FORMAT, SRB_UNKNOWN_DEVICE_COMMAND, strmini/SRB_PROPOSE_STREAM_RATE, strmini/SRB_GET_STREAM_PROPERTY, SRB_READ_DATA, SRB_PROPOSE_STREAM_RATE, strmini/SRB_SET_DATA_FORMAT, SRB_SET_DATA_FORMAT, SRB_GET_STREAM_INFO, SRB_OPEN_DEVICE_INSTANCE, strmini/SRB_GET_DATA_INTERSECTION, strmini/SRB_PROPOSE_DATA_FORMAT, strmini/SRB_GET_STREAM_STATE, SRB_CLOSE_DEVICE_INSTANCE, strmini/SRB_NOTIFY_IDLE_STATE, strmini/SRB_OPEN_MASTER_CLOCK, SRB_INITIALIZE_DEVICE, strmini/SRB_BEGIN_FLUSH, SRB_INDICATE_MASTER_CLOCK, strmini/SRB_COMMAND, SRB_INITIALIZATION_COMPLETE, SRB_WRITE_DATA, strmini/SRB_CLOSE_DEVICE_INSTANCE, SRB_SET_STREAM_RATE, strmini/SRB_GET_DEVICE_PROPERTY, strmini/SRB_SURPRISE_REMOVAL, _SRB_COMMAND, strmini/SRB_CHANGE_POWER_STATE, strmini/SRB_UNINITIALIZE_DEVICE, strmini/SRB_PAGING_OUT_DRIVER, SRB_SET_DEVICE_PROPERTY, SRB_GET_DATA_INTERSECTION, SRB_SURPRISE_REMOVAL, strmini/SRB_SET_STREAM_RATE, SRB_SET_STREAM_PROPERTY, SRB_UNKNOWN_STREAM_COMMAND, strmini/SRB_STREAM_METHOD, stream.srb_command, strmini/SRB_GET_DATA_FORMAT, SRB_GET_STREAM_PROPERTY, SRB_END_FLUSH
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




### -field SRB_READ_DATA

Stream-specific code that specifies to read data from hardware.


### -field SRB_WRITE_DATA

Stream-specific code that specifies to write data to the hardware.


### -field SRB_GET_STREAM_STATE

Stream-specific code that specifies to get the state of the stream.


### -field SRB_SET_STREAM_STATE

Stream-specific code that specifies to set the state of the stream.


### -field SRB_SET_STREAM_PROPERTY

Stream-specific code that specifies to set a property of the stream.


### -field SRB_GET_STREAM_PROPERTY

Stream-specific code that specifies to get a property value for the stream.


### -field SRB_OPEN_MASTER_CLOCK

Stream-specific code that indicates that the master clock is on this stream.


### -field SRB_INDICATE_MASTER_CLOCK

Stream-specific code that specifies that the handle is supplied to the master clock.


### -field SRB_UNKNOWN_STREAM_COMMAND

Stream-specific code that specifies that the IRP function is unknown to the class driver.


### -field SRB_SET_STREAM_RATE

Stream-specific code that specifies that the rate is set at which the stream should run.


### -field SRB_PROPOSE_DATA_FORMAT

Stream-specific code that specifies that a new rate is proposed, it does not change the rate.


### -field SRB_CLOSE_MASTER_CLOCK

Stream-specific code that indicates that the master clock is closed.


### -field SRB_PROPOSE_STREAM_RATE

Stream-specific code that indicates a new rate is proposed, it does not change the rate.


### -field SRB_SET_DATA_FORMAT

Stream-specific code that sets a new data format.


### -field SRB_GET_DATA_FORMAT

Stream-specific code that returns the current data format.


### -field SRB_BEGIN_FLUSH

Stream-specific code that begins the flush state.


### -field SRB_END_FLUSH

Stream-specific code that ends the flush state.


### -field SRB_GET_STREAM_INFO

Device instance-specific code that gets the stream information structure.


### -field SRB_OPEN_STREAM

Device instance-specific code that opens the specified stream.


### -field SRB_CLOSE_STREAM

Device instance-specific code that closes the specific stream.


### -field SRB_OPEN_DEVICE_INSTANCE

Device instance-specific code that opens an instance of the device.


### -field SRB_CLOSE_DEVICE_INSTANCE

Device instance-specific code that closes an instance of the device.


### -field SRB_GET_DEVICE_PROPERTY

Device instance-specific code that gets the property of the device.


### -field SRB_SET_DEVICE_PROPERTY

Device instance-specific code that sets the property of the device.


### -field SRB_INITIALIZE_DEVICE

Device instance-specific code that initializes the device.


### -field SRB_CHANGE_POWER_STATE

Device instance-specific code that changes the power state.


### -field SRB_UNINITIALIZE_DEVICE

Device instance-specific code that uninitializes the device.


### -field SRB_UNKNOWN_DEVICE_COMMAND

Device instance-specific code that specifies that the IRP function is unknown to the class driver.


### -field SRB_PAGING_OUT_DRIVER

Device instance-specific code that indicates that the driver is to be paged out only if it is enabled in the registry. Board ints should be disabled and STATUS_SUCCESS returned.


### -field SRB_GET_DATA_INTERSECTION

Device instance-specific code that returns stream data intersection.


### -field SRB_INITIALIZATION_COMPLETE

Device instance-specific code that indicates that the initialization sequence has completed.


### -field SRB_SURPRISE_REMOVAL

Device instance-specific code that indicates a surprise removal of hardware has occurred.


### -field SRB_DEVICE_METHOD



### -field SRB_STREAM_METHOD



### -field SRB_NOTIFY_IDLE_STATE

Device instance-specific code that specifies to call on first open and last close.

