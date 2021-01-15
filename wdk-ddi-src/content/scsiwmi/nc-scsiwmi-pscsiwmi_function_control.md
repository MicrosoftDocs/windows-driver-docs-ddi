---
UID: NC:scsiwmi.PSCSIWMI_FUNCTION_CONTROL
title: PSCSIWMI_FUNCTION_CONTROL (scsiwmi.h)
description: A miniport driver's HwScsiWmiFunctionControl routine is called to enable or disable notification of events.
old-location: storage\hwscsiwmifunctioncontrol.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PSCSIWMI_FUNCTION_CONTROL callback function"]
ms.keywords: HwScsiWmiFunctionControl, HwScsiWmiFunctionControl callback function [Storage Devices], PSCSIWMI_FUNCTION_CONTROL, PSCSIWMI_FUNCTION_CONTROL callback, Scsimini_42361f5c-fc45-4883-997e-afa65bc376c4.xml, scsiwmi/HwScsiWmiFunctionControl, storage.hwscsiwmifunctioncontrol
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
 - PSCSIWMI_FUNCTION_CONTROL
 - scsiwmi/PSCSIWMI_FUNCTION_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - scsiwmi.h
api_name:
 - PSCSIWMI_FUNCTION_CONTROL
---

# PSCSIWMI_FUNCTION_CONTROL callback function


## -description

A miniport driver's <b>HwScsiWmiFunctionControl</b> routine is called to enable or disable notification of events. It is also called to enable or disable data collection for data blocks that the miniport driver designated as expensive to collect. This routine is optional.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param DeviceContext 

[in]
Points to the miniport driver-defined context value passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param RequestContext 

[in]
Points to a value containing an enumerator value of type <a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmi_request_context">SCSIWMI_REQUEST_CONTEXT</a> that the miniport driver passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param GuidIndex 

[in]
Specifies the block by its index into the list of GUIDs in the SCSI_WMILIB_CONTEXT structure that the miniport driver passed to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>.

### -param Function 

[in]
Specifies <b>ScsiWmiEventControl</b> to enable or disable an event, or <b>ScsiWmiDataBlockControl</b> to enable or disable data collection for a block that was registered as expensive to collect (that is, a block for which the miniport driver set WMIREG_FLAG_EXPENSIVE in <b>Flags</b> of the SCSIWMIGUIDREGINFO structure used to register the block).

### -param Enable 

[in]
Specifies <b>TRUE</b> to enable the event or data collection, or <b>FALSE</b> to disable it.

## -returns

<b>HwScsiWmiFunctionControl</b> returns SRB_STATUS_PENDING if the request is pending, or a nonzero SRB status value if the request was completed.  The SRB status value returned by this routine is the same as what was passed in to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>. Although the return value data type is BOOLEAN, the <b>HwScsiWmiFunctionControl</b> routine actually returns an SRB status value.

## -remarks

When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb->WmiSubFunction</b>. The SCSI port driver calls a miniport driver's <b>HwScsiWmiFunctionControl</b> routine if <i>MinorFunction</i> indicates a request to enable or disable an event, or to enable or disable collection for a data block that the miniport driver registered as expensive to collect.

If a miniport driver does not implement a <b>HwScsiWmiFunctionControl</b> routine, it must set <b>WmiFunctionControl</b> to <b>NULL</b> in the SCSI_WMILIB_CONTEXT the miniport driver passes to <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>. The port driver returns SRB_STATUS_SUCCESS to the caller.

It is unnecessary for the miniport driver to check whether events or data collection are already enabled for a block because the port driver sends a single enable request when the first data consumer enables the block, and sends a single disable request when the last data consumer disables the block. The port driver will not call <b>HwScsiWmiFunctionControl</b> more than once to enable a block without an intervening call to disable it. 

If the SRB is completed in the <b>HwScsiWmiFunctionControl</b> callback, then the miniport driver calls <a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a> with an appropriate <i>SrbStatus</i>. If the miniport driver pends this SRB, then it should call <b>ScsiPortWmiPostProcess</b> when the SRB is done and before completing the SRB.

## -see-also

<a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmiguidreginfo">SCSIWMIGUIDREGINFO</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-_scsiwmilib_context">SCSI_WMILIB_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>



<a href="/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmipostprocess">ScsiPortWmiPostProcess</a>

