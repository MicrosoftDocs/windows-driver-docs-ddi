---
UID: NF:scsiwmi.ScsiPortWmiSetInstanceName
title: ScsiPortWmiSetInstanceName function (scsiwmi.h)
description: The ScsiPortWmiSetInstanceName routine updates the WNODE_ALL_DATA structure within the request context to specify the position and length of an instance name.
old-location: storage\scsiportwmisetinstancename.htm
tech.root: storage
ms.assetid: f624959f-e232-4918-8f0b-f232471c2c67
ms.date: 03/29/2018
keywords: ["ScsiPortWmiSetInstanceName function"]
ms.keywords: ScsiPortWmiSetInstanceName, ScsiPortWmiSetInstanceName routine [Storage Devices], scsiprt_a6ff8339-8734-4635-a17e-c3ad7bb524c3.xml, scsiwmi/ScsiPortWmiSetInstanceName, storage.scsiportwmisetinstancename
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiPortWmiSetInstanceName
 - scsiwmi/ScsiPortWmiSetInstanceName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsiwmi.h
api_name:
 - ScsiPortWmiSetInstanceName
---

# ScsiPortWmiSetInstanceName function


## -description

The <b>ScsiPortWmiSetInstanceName</b> routine updates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure within the request context to specify the position and length of an instance name. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param RequestContext 

[in]
Pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB.

### -param InstanceIndex 

[in]
Contains an index that indicates the instance for which the position and length of the instance name are to be specified.

### -param InstanceNameLength 

[in]
Specifies the size in bytes of the instance name.

### -param BufferAvail 

[out]
Must contain, on input, the number of bytes of buffer space in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure that can be used for describing instance names and data. On return, this member contains the number of bytes of buffer space that remain. 

There are three SCSI Port WMI routines that return a value for the available buffer size in their <i>BufferAvail </i>parameter:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetdata">ScsiPortWmiSetData</a>


<b>ScsiPortWmiSetInstanceName</b>

The miniport driver must call <b>ScsiPortWmiSetInstanceCount</b> first, but after <b>ScsiPortWmiSetInstanceCount</b> has been called, it does not matter in what order the minidriver calls <b>ScsiPortWmiSetData</b> and <b>ScsiPortWmiSetInstanceName</b>. When calling either <b>ScsiPortWmiSetData</b> or <b>ScsiPortWmiSetInstanceName</b>, the value passed to the routine in its <i>BufferAvail </i>parameter must be the same as the value returned in the <i>BufferAvail </i>parameter by the most recently called SCSI Port WMI routine. For instance, suppose the minidriver calls <b>ScsiPortWmiSetInstanceCount</b> first, and this routine returns a value of 1,000 in its <i>BufferAvail </i>parameter. Next, the minidriver calls <b>ScsiPortWmiSetData</b> which returns a value of 500 in its <i>BufferAvail </i>parameter. Finally, the minidriver calls <b>ScsiPortWmiSetInstanceName</b> which returns a value of 200 in its <i>BufferAvail </i>parameter. The initial value of 1,000 must be passed to <b>ScsiPortWmiSetData</b> in <i>BufferAvail</i>, and the value of 500 must be passed to <b>ScsiPortWmiSetInstanceName</b>. 

If there is not enough memory available to add an instance name of length <i>InstanceNameLength</i>, a zero will be returned in the <i>BufferAvail</i> member.

### -param SizeNeeded 

[in, out]
Indicates, on input, the number of bytes needed to describe the WNODE <i>before </i>adding the descriptive data for the instance specified by <i>InstanceIndex</i>. On return, this member will contain the size of the entire WNODE, including the data for the new instance.

## -returns

The <b>ScsiPortWmiSetInstanceCount</b> routine returns a pointer to the buffer where the caller can store the name of the instance specified in <i>InstanceIndex</i>. If <b>ScsiPortWmiSetInstanceCount</b> cannot allocate enough memory for the instance name, or if the WNODE contained within the request context is not of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>, <b>ScsiPortWmiSetData</b> returns <b>NULL</b>.

## -remarks

The minidriver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmisetinstancecount">ScsiPortWmiSetInstanceCount</a> before calling  <b>ScsiPortWmiSetInstanceName</b>.

The parameter <b>RequestContext</b> points to a request context structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wmi-wnode-xxx-structures">WMI WNODE_XXX Structures</a> used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The <b>ScsiPortWmiSetInstanceName</b> routine requires the WNODE structure that is defined within the request context to be of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>. This is because <b>ScsiPortWmiSetInstanceName</b> can set aside an instance name area for any of the instances associated with a WMI data block. Unlike the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure which contains information about a single instance, the WNODE_ALL_DATA structure contains an array of pointers to buffer areas for different instances, and <b>ScsiPortWmiSetInstanceCount</b> initializes this array, so that each buffer of instance data can be accessed individually.

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a>

