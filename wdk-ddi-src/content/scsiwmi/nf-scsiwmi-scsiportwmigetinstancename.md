---
UID: NF:scsiwmi.ScsiPortWmiGetInstanceName
title: ScsiPortWmiGetInstanceName function (scsiwmi.h)
description: The ScsiPortWmiGetInstanceName routine returns a pointer to the instance name associated with the indicated the Windows Management Instrumentation (WMI) SCSI Request Block (SRB).
old-location: storage\scsiportwmigetinstancename.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ScsiPortWmiGetInstanceName function"]
ms.keywords: ScsiPortWmiGetInstanceName, ScsiPortWmiGetInstanceName routine [Storage Devices], scsiprt_184c6508-4189-4ab2-a445-7e52e5c688ab.xml, scsiwmi/ScsiPortWmiGetInstanceName, storage.scsiportwmigetinstancename
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
 - ScsiPortWmiGetInstanceName
 - scsiwmi/ScsiPortWmiGetInstanceName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsiwmi.h
api_name:
 - ScsiPortWmiGetInstanceName
---

# ScsiPortWmiGetInstanceName function


## -description

The <b>ScsiPortWmiGetInstanceName</b> routine returns a pointer to the instance name associated with the indicated the <a href="/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a> (WMI) SCSI Request Block (SRB). 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param RequestContext 

[in]
Pointer to a structure of type <a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that contains the request context for a WMI SRB.

## -returns

Pointer to a counted string containing the instance name associated with the indicated SRB.  If the SRB type is one that does not use an instance name, <b>ScsiPortWmiGetInstanceName</b> returns <b>NULL</b>.

## -remarks

The parameter <b>RequestContext</b> points to a request context structure, <a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>, that contains information associated with a <a href="/windows-hardware/drivers/kernel/implementing-wmi">Windows Management Instrumentation</a> (WMI) SCSI request block (SRB). The request context structure, in turn, contains one of the <a href="/windows-hardware/drivers/kernel/wmi-wnode-xxx-structures">WMI WNODE_XXX Structures</a> that is used by the WMI system to pass data between user-mode data consumers and kernel-mode data providers such as drivers. 

The WNODE_XXX structure contained in the request context holds an instance name associated with the WMI SRB. The miniport driver calls <b>ScsiPortWmiGetInstanceName</b> to extract this instance name from the request context. 

The memory allocated for the request context must remain valid until after the miniport driver calls <b>ScsiPortWmiPostProcess</b>, and <b>ScsiPortWmiPostProcess</b> returns the final SRB status and buffer size. If the SRB can pend, the memory for the request context should be allocated from the SRB extension. If the SRB cannot pend, the memory can be allocated from a stack frame that does not go out of scope.

## -see-also

<a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_all_data">WNODE_ALL_DATA</a>



<a href="/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_single_instance">WNODE_SINGLE_INSTANCE</a>
