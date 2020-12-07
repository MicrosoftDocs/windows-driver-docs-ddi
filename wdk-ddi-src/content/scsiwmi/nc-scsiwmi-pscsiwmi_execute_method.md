---
UID: NC:scsiwmi.PSCSIWMI_EXECUTE_METHOD
title: PSCSIWMI_EXECUTE_METHOD (scsiwmi.h)
description: A miniport driver's HwScsiWmiExecuteMethod routine is called to execute a method associated with a data block.
old-location: storage\hwscsiwmiexecutemethod.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PSCSIWMI_EXECUTE_METHOD callback function"]
ms.keywords: HwScsiWmiExecuteMethod, HwScsiWmiExecuteMethod callback function [Storage Devices], PSCSIWMI_EXECUTE_METHOD, PSCSIWMI_EXECUTE_METHOD callback, Scsimini_a0b3e943-a363-478d-9d68-09acf0c5b591.xml, scsiwmi/HwScsiWmiExecuteMethod, storage.hwscsiwmiexecutemethod
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
 - PSCSIWMI_EXECUTE_METHOD
 - scsiwmi/PSCSIWMI_EXECUTE_METHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - scsiwmi.h
api_name:
 - HwScsiWmiExecuteMethod
---

# PSCSIWMI_EXECUTE_METHOD callback function


## -description

A miniport driver's <b>HwScsiWmiExecuteMethod</b> routine is called to execute a method associated with a data block. This routine is optional.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param DeviceContext 

[in]
Points to the miniport driver-defined context value passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param RequestContext 

[in]
Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param GuidIndex 

[in]
Specifies the data block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param InstanceIndex 

[in]
If the block specified by <i>GuidIndex</i> has multiple instances, <i>InstanceIndex</i> specifies the instance.

### -param MethodId 

[in]
Specifies the ID of the method to execute. The miniport driver defines the method ID as an item in a data block.

### -param InBufferSize 

[in]
Indicates the size in bytes of the input data. If there is no input data, <i>InBufferSize</i> is zero.

### -param OutBufferSize 

[in]
Indicates the number of bytes available in the buffer for output data.

### -param Buffer 

[in, out]
Points to a buffer that holds the input data and receives the output data, if any, from the method. If the buffer is too small to receive all of the output, the miniport driver calls <b>ScsiPortWmiPostProcess</b> with SRB_STATUS_DATA_OVERRUN and the size required.

## -returns

<b>HwScsiWmiExecuteMethod</b> returns SRB_STATUS_PENDING if the request is pending, or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>. Although the return value data type is BOOLEAN, the <b>HwScsiWmiExecuteMethod</b> routine actually returns an SRB status value.

## -remarks

When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb->WmiSubFunction</b>. The SCSI port driver calls the miniport driver's <b>HwScsiWmiExecuteMethod</b> routine if <i>MinorFunction</i> indicates a request to execute a method.

If a miniport driver does not implement a <b>HwScsiWmiExecuteMethod</b> routine, it must set <b>ExecuteWmiMethod</b> to <b>NULL</b> in the SCSI_WMILIB_CONTEXT the miniport driver passes to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>. In this case, the port driver returns SRB_STATUS_ERROR to the caller.

If the method generates output, the miniport driver should check the size of the output buffer in <i>OutBufferSize</i> before performing any operation that might have side effects or that should not be performed twice. For example, if a method returns the values of a group of counters and then resets the counters, the miniport driver should check the buffer size before resetting the counters. This ensures that the port driver can safely resend the request with a larger buffer. If the buffer is too small, the miniport driver should call <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a> with SRB_STATUS_DATA_OVERRUN and the size of the output buffer needed to fulfill the request. 

The miniport driver executes the method and writes output, if any, to the buffer. Before returning from <b>HwScsiWmiExecuteMethod</b>, the miniport driver calls <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i> value and the number of bytes used in the output buffer.

## -see-also

<a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-_scsiwmilib_context">SCSI_WMILIB_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>
