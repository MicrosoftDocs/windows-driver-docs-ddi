---
UID: NS:ks._KSPIN_DESCRIPTOR_EX
title: "_KSPIN_DESCRIPTOR_EX"
author: windows-driver-content
description: The KSPIN_DESCRIPTOR_EX structure describes the characteristics of a pin type on a given filter type.
old-location: stream\kspin_descriptor_ex.htm
old-project: stream
ms.assetid: 05c82973-86f9-44f9-8df2-1fc84c8be975
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPIN_DESCRIPTOR_EX, KSPIN_DESCRIPTOR_EX, KSPIN_DESCRIPTOR_EX structure [Streaming Media Devices], KSPIN_FLAG_ASYNCHRONOUS_PROCESSING, KSPIN_FLAG_CRITICAL_PROCESSING, KSPIN_FLAG_DENY_USERMODE_ACCESS, KSPIN_FLAG_DISPATCH_LEVEL_PROCESSING, KSPIN_FLAG_DISTINCT_TRAILING_EDGE, KSPIN_FLAG_DO_NOT_INITIATE_PROCESSING, KSPIN_FLAG_DO_NOT_USE_STANDARD_TRANSPORT, KSPIN_FLAG_ENFORCE_FIFO, KSPIN_FLAG_FIXED_FORMAT, KSPIN_FLAG_FRAMES_NOT_REQUIRED_FOR_PROCESSING, KSPIN_FLAG_GENERATE_EOS_EVENTS, KSPIN_FLAG_GENERATE_MAPPINGS, KSPIN_FLAG_HYPERCRITICAL_PROCESSING, KSPIN_FLAG_IMPLEMENT_CLOCK, KSPIN_FLAG_INITIATE_PROCESSING_ON_EVERY_ARRIVAL, KSPIN_FLAG_PROCESS_IF_ANY_IN_RUN_STATE, KSPIN_FLAG_PROCESS_IN_RUN_STATE_ONLY, KSPIN_FLAG_RENDERER, KSPIN_FLAG_SOME_FRAMES_REQUIRED_FOR_PROCESSING, KSPIN_FLAG_SPLITTER, KSPIN_FLAG_USE_STANDARD_TRANSPORT, PKSPIN_DESCRIPTOR_EX, PKSPIN_DESCRIPTOR_EX structure pointer [Streaming Media Devices], _KSPIN_DESCRIPTOR_EX, avstruct_6a73afe1-d131-47fc-877b-1abff4a75833.xml, ks/KSPIN_DESCRIPTOR_EX, ks/PKSPIN_DESCRIPTOR_EX, stream.kspin_descriptor_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	KSPIN_DESCRIPTOR_EX
product: Windows
targetos: Windows
req.typenames: KSPIN_DESCRIPTOR_EX, *PKSPIN_DESCRIPTOR_EX
---

# _KSPIN_DESCRIPTOR_EX structure


## -description


The KSPIN_DESCRIPTOR_EX structure describes the characteristics of a pin type on a given filter type.


## -struct-fields




### -field Dispatch

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a> structure for this pin. This pointer is optional and should only be provided by clients that wish to receive notifications. Clients that need to perform pin-centric processing (filters concerned with the routing of data, in other words hardware drivers) must provide this dispatch table and a process dispatch. See <b>KSPIN_DISPATCH</b> for more information.


### -field AutomationTable

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560990">KSAUTOMATION_TABLE</a> structure for this pin. The automation table contains the properties, methods, and events supported by the pin. This automation table is merged with the automation table provided by AVStream for all pins. If the client supplies any property, event, or method handlers that are already provided by AVStream, the client's implementation supersedes that of AVStream.


### -field PinDescriptor

This member specifies a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a>.


### -field Flags

Specifies a value of type ULONG. This can be any combination of the flags listed in the following list. Specify flags using a bitwise OR, with the following exceptions: KSPIN_FLAG_CRITICAL_PROCESSING and KSPIN_FLAG_HYPERCRITICAL_PROCESSING are mutually exclusive. KSPIN_FLAG_DO_NOT_INITIATE_PROCESSING and KSPIN_FLAG_INITIATE_PROCESSING_ON_EVERY_ARRIVAL are mutually exclusive. KSPIN_FLAG_FRAMES_NOT_REQUIRED_FOR_PROCESSING and KSPIN_FLAG_SOME_FRAMES_REQUIRED_FOR_PROCESSING are mutually exclusive. KSPIN_FLAG_PROCESS_IN_RUN_STATE_ONLY and KSPIN_FLAG_PROCESS_IF_ANY_IN_RUN_STATE are mutually exclusive.



#### KSPIN_FLAG_DISPATCH_LEVEL_PROCESSING

Indicates that the minidriver requests that the process dispatch to happen at IRQL DISPATCH_LEVEL instead of PASSIVE_LEVEL.



#### KSPIN_FLAG_CRITICAL_PROCESSING

If asynchronous processing has been specified or if the system is running at PASSIVE_LEVEL and a process call comes in at DISPATCH_LEVEL, processing is done in a queued work item. This flag indicates that the work item should be placed on the critical work queue as opposed to the delayed work queue.



#### KSPIN_FLAG_HYPERCRITICAL_PROCESSING

If asynchronous processing has been specified or if the system is running at PASSIVE_LEVEL and a process call comes in at DISPATCH_LEVEL, processing is done in a queued work item. This flag indicates that the work item should be placed on the hypercritical work queue as opposed to the delayed work queue or critical work queue.



#### KSPIN_FLAG_ASYNCHRONOUS_PROCESSING

Indicates that the pin should process data asynchronously. If this flag is set, AVStream does not wait for one process dispatch to be called before proceeding with additional frames.



#### KSPIN_FLAG_DO_NOT_INITIATE_PROCESSING

AVStream calls the processing dispatch only when the minidriver explicitly calls <b>Ks</b><i>Xxx</i><b>AttemptProcessing</b>. Useful for clients that intend to directly poll the queue at, for example, DPC time to transport data to hardware.



#### KSPIN_FLAG_INITIATE_PROCESSING_ON_EVERY_ARRIVAL

Indicates that processing should occur every time a data frame arrives into the queue. If this flag is not specified, the process dispatch is only called when data arrives into a previously empty queue.



#### KSPIN_FLAG_FRAMES_NOT_REQUIRED_FOR_PROCESSING

Indicates that frames are not required on this pin for processing to commence. Even if no frames exist in the queue, a state change will now suffice to cause AVStream to call the processing dispatch. This flag is useful only for filter-centric filters. Pins that do not specify this flag delay processing on the filter if they do not have available frames. Pins that do specify this flag do not delay processing in this manner. If a pin specifies this flag, it becomes the responsibility of the process dispatch to check for available frames.



#### KSPIN_FLAG_ENFORCE_FIFO

Specifying this flag causes the queue to force IRPs to be handled in a first-in-first-out manner. If one IRP is completed by the minidriver prior to an IRP that was sent earlier, the later IRP is not completed by AVStream until the earlier IRP has been completed by the minidriver.



#### KSPIN_FLAG_GENERATE_MAPPINGS

Specifying this flag causes AVStream to automatically generate scatter/gather mappings for a queued frame when the minidriver locks a stream pointer referencing that frame. Clients that intend to use this feature need to register their DMA adapter object with AVStream via the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561687">KsDeviceRegisterAdapterObject</a> function. See the <b>DataUsed</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a> for the effect of this flag on the KSSTREAM_HEADER structure. Also see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567140">KSSTREAM_POINTER_OFFSET</a>.



#### KSPIN_FLAG_DISTINCT_TRAILING_EDGE

Indicates that the queue associated with the pin should have a trailing edge stream pointer. The trailing edge pointer is a special stream pointer that points to the oldest data in the queue unless clone pointers exist on older data. Any data frames in the window between the leading and trailing edge stream pointers are considered to have at least one reference count on them and are not completed until they move out of the window by advancing the trailing edge with <a href="https://msdn.microsoft.com/library/windows/hardware/ff563518">KsPinGetTrailingEdgeStreamPointer</a> and one of the <b>KsStreamPointerAdvance</b><i>Xxx</i> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567137">KsStreamPointerUnlock</a> functions. Pins that do not specify this flag do not have a trailing edge stream pointer.



#### KSPIN_FLAG_PROCESS_IN_RUN_STATE_ONLY

Indicates that AVStream should only call this pin to process when the pin is in KSSTATE_RUN. Changes the minimum processing state from pause to run. AVStream calls this pin to process <i>after</i> telling it to go to run state, even if frames arrive. Any pin that specifies this flag and is part of a filter-centric filter causes the filter not to process if the given pin is not in KSSTATE_RUN.



#### KSPIN_FLAG_SPLITTER

Indicates that this pin (an output pin) is a splitter. Pins that specify this flag should indicate a number of possible instances greater than one. When a second instance of this pin is created, AVStream automatically sets up a splitter so that frames sent to the original pin are copied to the new pin. Note that this copying is done automatically by AVStream. Clients <i>typically</i> can ignore process pins that have non-<b>NULL</b><b>DelegateBranch</b> and <b>CopySource</b> pointers. These members indicate that the pin is part of a splitter branch and is handled automatically by AVStream. In releases post-DirectX 8.0, this flag works for pins on both filter-centric and pin-centric filters. Older releases support this flag only for pins on filter-centric filters.



#### KSPIN_FLAG_USE_STANDARD_TRANSPORT

This flag forces the pin to use the standard transport mechanism. It overrides all other checks (communication type, medium type, interface type, etc.) on the pin. Specifying both this flag and KSPIN_FLAG_DO_NOT_USE_STANDARD_TRANSPORT results in the standard transport being used. This flag overrides all other checks.



#### KSPIN_FLAG_DO_NOT_USE_STANDARD_TRANSPORT

Indicates that the pin does not use the standard transport mechanism. Pins that do not use the standard transport mechanism will not belong to a pipe section and will not have associated queues.



#### KSPIN_FLAG_FIXED_FORMAT

Indicates that this pin uses a fixed data format. Any attempt to set the data format returns STATUS_INVALID_DEVICE_REQUEST.



#### KSPIN_FLAG_GENERATE_EOS_EVENTS

Indicates that this pin handles connection event support requests.



#### KSPIN_FLAG_RENDERER

Specifies that this pin is capable of rendering frames.



#### KSPIN_FLAG_SOME_FRAMES_REQUIRED_FOR_PROCESSING

When specified on a filter-centric filter pin, indicates that one or more instances of the pin type in question must have frames available in order to process data. Mutually exclusive with KSPIN_FLAG_FRAMES_NOT_REQUIRED_FOR_PROCESSING.

Note that this behavior can be obtained through <a href="https://msdn.microsoft.com/library/windows/hardware/ff563492">KsPinAttachOrGate</a> by manually setting up an OR gate as the frame gate for every instance of the pin and attaching this OR gate to the filter's AND gate.

When using this flag, minidrivers cannot call <a href="https://msdn.microsoft.com/library/windows/hardware/ff563491">KsPinAttachAndGate</a> or <b>KsPinAttachOrGate</b> on the associated pin instances. (The flag effectively does this for you for the simple OR case.) Also see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.



#### KSPIN_FLAG_PROCESS_IF_ANY_IN_RUN_STATE

When specified on a <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">filter-centric</a> pin, indicates that processing may occur when one or more of the pin instances so flagged are in the run state. All nonstopped pins still must be in at least pause to process data. Do not use this flag if the corresponding pin is an output pin and this pin is involved in an in-place transform.



#### KSPIN_FLAG_DENY_USERMODE_ACCESS

This flag prevents user-mode access to this specific pin.



#### KSPIN_FLAG_IMPLEMENT_CLOCK

Indicates that this pin exposes a clock that can be selected by the graph manager as a master clock. Also see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.


### -field InstancesPossible

Specifies a value of type ULONG that contains a count of the maximum number of possible instances of this pin. Any attempt to instantiate more than this number of pins of the given type fails. Set to KSINSTANCE_INDETERMINATE to have no limit on number of pins instantiated.


### -field InstancesNecessary

Specifies a value of type ULONG that contains the minimum number of pins of a given pin type that are required to be in a state at or above the minimum processing level for proper functioning of the filter. By default the minimum processing level is KSSTATE_PAUSE, although the minidriver can modify the default behavior by setting the <b>Flags</b> member of this structure to either KSPIN_FLAG_PROCESS_IN_RUN_STATE_ONLY or KSPIN_FLAG_PROCESS_IF_ANY_IN_RUN_STATE. Any attempt to change the state of a filter that does not have this number of instances of this type of pin fails. See additional information in the Remarks section.


### -field AllocatorFraming

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560982">KSALLOCATOR_FRAMING_EX</a> structure containing the allocator framing requirements for this pin type. Allocator framing specifies items such as memory alignment requirements, maximum frame size, and minimum frame size. This member can be <b>NULL</b>, which indicates that this pin does not support the allocator framing property.


### -field IntersectHandler

A pointer to a driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567185">KStrIntersectHandlerEx</a> function to handle data-intersection. If this member is <b>NULL</b>, the pin handles data intersection queries for data ranges with the specifier KSDATAFORMAT_SPECIFIER_NONE. The intersection handler function receives a single data range from the query and a single data range from the pins list of data ranges. The type, subtype, and specifier GUIDs of these ranges are guaranteed to match, though some may be wildcards. The function either indicates the data ranges do not match, or it produces the best data format in the intersection of the two data ranges. See <a href="https://msdn.microsoft.com/44281574-8258-47a3-857d-fd44bb949f17">Data Range Intersections in AVStream</a> for more information.


## -remarks



<div class="alert"><b>Note</b>    AMCap and Blink might not be able to find tuner and crossbar interfaces on your AVStream driver if the <b>InstancesNecessary</b> member of KSPIN_DESCRIPTOR_EX is set to zero for the analog video input pin. To fix this problem, set <b>InstancesNecessary</b> for this pin to one.</div>
<div> </div>
Note that the allocator framing requirements of your pin may be ignored despite the fact that your allocator framing specifies that alignment or size is absolutely required to be a certain value. If your kernel-mode driver is connected to an upstream user-mode filter that allocates for it and the particular upstream filter's allocator does not understand framing requirements, this can happen (current particular examples include the MPEG-2 splitter).

Furthermore, if you specify KSPIN_FLAG_DO_NOT_INITIATE_PROCESSING and the pin uses the standard transport mechanism, you must have a processing object. This means there must be some process dispatch provided (either at the filter level or at the pin level); even if this function is never called, it must be provided in this circumstance.


<a href="https://msdn.microsoft.com/44281574-8258-47a3-857d-fd44bb949f17">Data Range Intersections in AVStream</a> and <a href="https://msdn.microsoft.com/c2cfc183-0f4c-4104-a580-234e0483eee4">AVStream Splitters</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560982">KSALLOCATOR_FRAMING_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561687">KsDeviceRegisterAdapterObject</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPIN_DESCRIPTOR_EX structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

