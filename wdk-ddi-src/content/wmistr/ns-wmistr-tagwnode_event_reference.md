---
UID: NS:wmistr.tagWNODE_EVENT_REFERENCE
title: tagWNODE_EVENT_REFERENCE (wmistr.h)
description: The WNODE_EVENT_REFERENCE structure contains information that WMI can use to query for an event that exceeds the event size limit set in the registry.
old-location: kernel\wnode_event_reference.htm
tech.root: kernel
ms.assetid: 9dfe75e5-301e-4378-a2ad-f43676d8c208
ms.date: 04/30/2018
keywords: ["tagWNODE_EVENT_REFERENCE structure"]
ms.keywords: "*PWNODE_EVENT_REFERENCE, PWNODE_EVENT_REFERENCE, PWNODE_EVENT_REFERENCE structure pointer [Kernel-Mode Driver Architecture], WNODE_EVENT_REFERENCE, WNODE_EVENT_REFERENCE structure [Kernel-Mode Driver Architecture], kernel.wnode_event_reference, kstruct_d_cf8551b3-5506-4c02-b56a-a4836429d5e1.xml, tagWNODE_EVENT_REFERENCE, wmistr/PWNODE_EVENT_REFERENCE, wmistr/WNODE_EVENT_REFERENCE"
f1_keywords:
 - "wmistr/WNODE_EVENT_REFERENCE"
 - "WNODE_EVENT_REFERENCE"
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
- Wmistr.h
api_name:
- WNODE_EVENT_REFERENCE
targetos: Windows
req.typenames: WNODE_EVENT_REFERENCE, *PWNODE_EVENT_REFERENCE
---

# tagWNODE_EVENT_REFERENCE structure


## -description


The <b>WNODE_EVENT_REFERENCE</b> structure contains information that WMI can use to query for an event that exceeds the event size limit set in the registry.


## -struct-fields




### -field WnodeHeader

Is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the provider ID, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field TargetGuid

Indicates the GUID that represents the event to query.


### -field TargetDataBlockSize

Indicates the size of the event.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.TargetInstanceIndex

Indicates the index into the driver's list of static instance names for the event. This member is valid only if the event block was registered with static instance names and WNODE_FLAGS_STATIC_INSTANCE_NAMES is set in <b>WnodeHeader.Flags</b>.


### -field DUMMYUNIONNAME.TargetInstanceName

Indicates the dynamic instance name of the event as a counted Unicode string. This member is valid only if WNODE_FLAGS_STATIC_INSTANCE_NAMES is clear in <b>WnodeHeader.Flags</b> and the event block was registered with dynamic instance names.


## -remarks



If the amount of data for an event exceeds the maximum size set in the registry, a driver can generate a <b>WNODE_EVENT_REFERENCE</b> that specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a> that WMI can query to obtain the event. For more information about defining and generating WMI events, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-wmi">Implementing WMI</a>.

The <b>ProviderId</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure for use in a <b>WNODE_EVENT_REFERENCE</b> structure should be initialized using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmideviceobjecttoproviderid">IoWMIDeviceObjectToProviderId</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmideviceobjecttoproviderid">IoWMIDeviceObjectToProviderId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a>
 

 

