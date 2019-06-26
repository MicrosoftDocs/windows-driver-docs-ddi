---
UID: NF:scsiwmi.ScsiPortWmiSetInstanceCount
title: ScsiPortWmiSetInstanceCount function (scsiwmi.h)
description: The ScsiPortWmiSetInstanceCount specifies the number of instances for which data buffers must be set aside within the WNODE_ALL_DATA structure in the request context.
old-location: storage\scsiportwmisetinstancecount.htm
tech.root: storage
ms.assetid: 0de2c766-cd3c-46ff-bb78-f1e4c37af2c0
ms.date: 03/29/2018
ms.keywords: ScsiPortWmiSetInstanceCount, ScsiPortWmiSetInstanceCount function [Storage Devices], scsiprt_9451dca5-cc2f-43fa-91c6-3c22f6377a13.xml, scsiwmi/ScsiPortWmiSetInstanceCount, storage.scsiportwmisetinstancecount
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsiwmi.h
api_name:
- ScsiPortWmiSetInstanceCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# ScsiPortWmiSetInstanceCount function


## -description


The <b>ScsiPortWmiSetInstanceCount</b> specifies the number of instances for which data buffers must be set aside within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a> structure in the request context. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param RequestContext [in]

Pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB. 


### -param InstanceCount [in]

Contains the number of instances for which the minidriver will provide data. 


### -param BufferAvail [out]

Contains, on return, the number of bytes of buffer space available for describing instance names and data. The value that is returned in this member can be passed to routines <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/nf-scsiwmi-scsiportwmisetdata">ScsiPortWmiSetData</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/nf-scsiwmi-scsiportwmisetinstancename">ScsiPortWmiSetInstanceName</a> in the <i>BufferAvail </i>parameter of those routines. 

The <b>ScsiPortWmiSetInstanceCount</b> routine initializes an array of pointers to data buffers, with one array element for each instance. If there is not enough memory available in the WNODE to initialize an array of size <i>InstanceCount</i>, a zero will be returned in this member. 


### -param SizeNeeded [out]

Indicates, on input, the number of bytes needed to describe the entire WNODE <i>before </i>configuring the internal arrays in the WNODE. On return, this member will contain the size of the entire WNODE, including the newly initialized arrays within the WNODE. 


## -returns



The <b>ScsiPortWmiSetInstanceCount</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the WNODE contained within the request context is not of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>.




## -remarks



The minidriver must call <b>ScsiPortWmiSetInstanceCount</b> before calling either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/nf-scsiwmi-scsiportwmisetdata">ScsiPortWmiSetData</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/nf-scsiwmi-scsiportwmisetinstancename">ScsiPortWmiSetInstanceName</a>. The minidriver should only call <b>ScsiPortWmiSetInstanceCount</b> once. 

The parameter <b>RequestContext</b> points to a request context structure, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/wmi-wnode-xxx-structures">WMI WNODE_XXX Structures</a> used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The <b>ScsiPortWmiSetInstanceCount</b> routine requires the WNODE structure that is defined within the request context to be of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>. This is because <b>ScsiPortWmiSetInstanceCount</b> sets aside a data area that will hold information for multiple instances associated with a WMI data block. Unlike the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a> structure which contains information about a single instance, the WNODE_ALL_DATA structure contains an array of pointers to buffer areas for different instances, and <b>ScsiPortWmiSetInstanceCount</b> initializes this array, so that each buffer of instance data can be accessed individually using an instance index.

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a>
 

 

