---
UID: NS:wmistr._WNODE_HEADER
title: _WNODE_HEADER (wmistr.h)
description: The WNODE_HEADER structure is the first member of all other WNODE_XXX structures. It contains information common to all such structures.
old-location: kernel\wnode_header.htm
tech.root: kernel
ms.assetid: a895f048-b111-4ccc-8466-fe9b169a2f95
ms.date: 04/30/2018
ms.keywords: "*PWNODE_HEADER, PWNODE_HEADER, PWNODE_HEADER structure pointer [Kernel-Mode Driver Architecture], WNODE_HEADER, WNODE_HEADER structure [Kernel-Mode Driver Architecture], _WNODE_HEADER, kernel.wnode_header, kstruct_d_ff879b76-aed0-46d5-a688-c59e1424aeb4.xml, wmistr/PWNODE_HEADER, wmistr/WNODE_HEADER"
ms.topic: struct
req.header: wmistr.h
req.include-header: Wmistr.h
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
- wmistr.h
api_name:
- WNODE_HEADER
product:
- Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
---

# _WNODE_HEADER structure


## -description


The <b>WNODE_HEADER</b> structure is the first member of all other <b>WNODE_<i>XXX</i></b> structures. It contains information common to all such structures.


## -struct-fields




### -field BufferSize

This member specifies the size, in bytes, of the nonpaged buffer to receive any <b>WNODE_<i>XXX</i></b> data to be returned, including this <b>WNODE_HEADER</b> structure, additional members of a <b>WNODE_<i>XXX</i></b> structure of the type indicated by <b>Flags</b>, and any WMI- or driver-determined data that accompanies that structure.


### -field ProviderId

If <b>Flags</b> is set to WNODE_FLAG_EVENT_ITEM or WNODE_FLAG_EVENT_REFERENCE, <b>ProviderId</b> should contain the ID of the WMI provider associated with the device object. You can obtain the <b>ProviderId</b> value by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmideviceobjecttoproviderid">IoWMIDeviceObjectToProviderId</a>. If <b>Flags</b> is set to any other value, this member is reserved.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.HistoricalContext

This member stores the handle to the event tracing session. 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Version

This member is reserved for WMI.


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.Linkage

This member is reserved for WMI. 


### -field DUMMYUNIONNAME2

 


### -field DUMMYUNIONNAME2.CountLost

Reserved


### -field DUMMYUNIONNAME2.KernelHandle

This member is reserved for WMI.


### -field DUMMYUNIONNAME2.TimeStamp

This member indicates the time at which a driver collected the <b>WNODE_<i>XXX</i></b> data. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar. A driver can call <b>KeQuerySystemTime</b> to obtain this value. If the block is to be written to a log file (WNODE_FLAG_LOG_WNODE), an NT driver might also set WNODE_FLAG_USE_TIMESTAMP in <b>Flags</b> to request that the system logger leave the value of <b>TimeStamp </b>unchanged. 


### -field Guid

This member indicates the GUID that represents the data block associated with the <b>WNODE_<i>XXX</i></b> to be returned. 


### -field ClientContext

This member stores the clock type for the session. Possible values are included in the following table. 

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
1

</td>
<td>
Performance counter value (also called QPC, QueryPerformanceCounter, or PerfCounter)

</td>
</tr>
<tr>
<td>
2

</td>
<td>
System timer

</td>
</tr>
<tr>
<td>
3

</td>
<td>
CPU cycle

</td>
</tr>
</table>
 


### -field Flags

This member indicates the type of <b>WNODE_<i>XXX</i></b> structure that contains the WNODE_HEADER structure:





#### WNODE_FLAG_ALL_DATA

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer. 

WMI sets this flag in the <b>WNODE_HEADER</b> structure that it passes with an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-all-data">IRP_MN_QUERY_ALL_DATA</a> request.

A driver sets this flag in the <b>WNODE_HEADER</b> structure of an event that consists of all instances of a data block. If the data block size is identical for all instances, a driver also sets WNODE_FLAG_FIXED_INSTANCE_SIZE.



#### WNODE_FLAG_EVENT_ITEM

A driver sets this flag to indicate that the <b>WNODE_<i>XXX</i></b> structure was generated as an event. This flag is valid only if WNODE_FLAG_ALL_DATA, WNODE_FLAG_SINGLE_INSTANCE, or WNODE_FLAG_SINGLE_ITEM is also set.



#### WNODE_FLAG_EVENT_REFERENCE

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_event_reference">WNODE_EVENT_REFERENCE</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer. 

A driver sets this flag when it generates an event that is larger than the maximum size specified in the registry for an event. WMI uses the information in the <b>WNODE_EVENT_REFERENCE</b> structure to request the event data and schedules such a request according to the value of WNODE_FLAG_SEVERITY_MASK.



#### WNODE_FLAG_METHOD_ITEM

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_method_item">WNODE_METHOD_ITEM</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer.

WMI sets this flag in the <b>WNODE_HEADER</b> structure that it passes with an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-execute-method">IRP_MN_EXECUTE_METHOD</a> request. 



#### WNODE_FLAG_SINGLE_INSTANCE

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer.

WMI sets this flag in the <b>WNODE_HEADER</b> structure that it passes with a request to query or change an instance.

A driver sets this flag in the <b>WNODE_HEADER</b> structure of an event that consists of a single instance of a data block. 



#### WNODE_FLAG_SINGLE_ITEM

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer.

WMI sets this flag in the <b>WNODE_HEADER</b> structure that it passes with a request to change an item.

A driver sets this flag in the <b>WNODE_HEADER</b> structure of an event that consists of a single data item.



#### WNODE_FLAG_TOO_SMALL

The rest of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_too_small">WNODE_TOO_SMALL</a> structure follows the <b>WNODE_HEADER</b> structure in the buffer.

A driver sets this flag when it passes a <b>WNODE_TOO_SMALL</b> structure, indicating that the buffer is too small for all of the <b>WNODE_<i>XXX</i></b> data to be returned.

In addition, <b>Flags</b> might be set with one or more of the following flags that provide additional information about the <b>WNODE_<i>XXX</i></b>: 





#### WNODE_FLAG_FIXED_INSTANCE_SIZE

All instances of a data block are the same size. This flag is valid only if WNODE_FLAG_ALL_DATA is also set. 



#### WNODE_FLAG_INSTANCES_SAME

The number of instances and the dynamic instance names in a <b>WNODE_ALL_DATA</b> structure to be returned are identical to those returned from the previous <b>WNODE_ALL_DATA</b> query. This flag is valid only if WNODE_FLAG_ALL_DATA is also set. This flag is ignored for data blocks registered with static instance names.

For optimized performance, a driver should set this flag if it can track changes to the number or names of its data blocks. WMI can then skip the processing required to detect and update dynamic instance names. 



#### WNODE_FLAG_STATIC_INSTANCE_NAMES

The <b>WNODE_<i>XXX</i></b> data to be returned does not include instance names.

WMI sets this flag before requesting <b>WNODE_<i>XXX</i></b> data for data blocks registered with static instance names. After receiving the returned <b>WNODE_<i>XXX</i></b> from the driver, WMI fills in the static instance names specified at registration before passing the returned <b>WNODE_<i>XXX</i></b> to a data consumer. 



#### WNODE_FLAG_PDO_INSTANCE_NAMES

Static instance names are based on the device instance ID of the PDO for the device. A driver requests such names by setting WMIREG_FLAG_INSTANCE_PDO in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-wmiregguidw">WMIREGGUID</a> it uses to register the block.

WMI sets this flag before requesting <b>WNODE_<i>XXX</i></b> data for data blocks registered with PDO-based instance names.



#### WNODE_FLAG_SEVERITY_MASK

The driver-determined severity level of the event associated with a returned <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_event_reference">WNODE_EVENT_REFERENCE</a>, with 0x00 indicating the least severe and 0xff indicating the most severe level.

WMI uses the value of this flag to prioritize its requests for the event data.



#### WNODE_FLAG_USE_TIMESTAMP

The system logger should not modify the value of <b>TimeStamp</b> set by the driver. 

An NT driver might also set <b>Flags</b> to one or more of the following values for event blocks to be written to a system log file:





#### WNODE_FLAG_LOG_WNODE

An event block is to be sent to the system logger. The event header is a standard <b>WNODE_HEADER</b> structure. If the driver clears WNODE_FLAG_TRACED_GUID, the block will also be sent to WMI for delivery to any data consumers that have enabled the event. The driver must allocate the <b>WNODE_<i>XXX</i></b> from pool memory. WMI frees the memory after delivering the event to data consumers.



#### WNODE_FLAG_TRACED_GUID

An event block is to be sent only to the system logger. It does not get sent to WMI data consumers. The event header is an <b>EVENT_TRACE_HEADER</b> structure, declared in <i>Evntrace.h</i>, instead of a <b>WNODE_HEADER</b>. The driver must allocate memory for the <b>WNODE_<i>XXX</i></b> and free it after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiwriteevent">IoWMIWriteEvent</a> returns. The driver can allocate such memory either from the stack or, to minimize the overhead of allocating and freeing the memory, from the driver's thread local storage if the driver creates and maintains its own thread pool.



#### WNODE_FLAG_USE_GUID_PTR

The <b>Guid</b> member points to a GUID in memory, rather than containing the GUID itself. The system logger dereferences the pointer before passing the data to the consumer. This flag is valid only if WNODE_FLAG_LOG_WNODE or WNODE_FLAG_TRACED_GUID are also set.



#### WNODE_FLAG_USE_MOF_PTR

Data that follows the fixed members of a <b>WNODE_<i>XXX</i></b> structure consists of an array of MOF_FIELD structures, defined in Evntrace.h, that contain pointers to data and sizes rather than the data itself. The array can contain up to MAX_MOF_FIELD elements. The system logger dereferences the pointers before passing the data to the consumer This flag is valid only for blocks registered with WMIREG_FLAG_TRACED_GUID. 


## -remarks



In an <b>IRP_MN_CHANGE_<i>XXX</i></b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-execute-method">IRP_MN_EXECUTE_METHOD</a> request, <b>BufferSize</b> in the IRP indicates the maximum size in bytes of the output buffer, while <b>BufferSize</b> in the input <b>WNODE_HEADER</b> for such a request indicates the size, in bytes, of the input data in the buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmideviceobjecttoproviderid">IoWMIDeviceObjectToProviderId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iowmiwriteevent">IoWMIWriteEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kequerysystemtime">KeQuerySystemTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_event_reference">WNODE_EVENT_REFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_method_item">WNODE_METHOD_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_item">WNODE_SINGLE_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_too_small">WNODE_TOO_SMALL</a>
 

 

