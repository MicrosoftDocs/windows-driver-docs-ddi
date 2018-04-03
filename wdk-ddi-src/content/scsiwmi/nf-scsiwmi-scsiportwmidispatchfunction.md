---
UID: NF:scsiwmi.ScsiPortWmiDispatchFunction
title: ScsiPortWmiDispatchFunction function
author: windows-driver-content
description: The ScsiPortWmiDispatchFunction routine is a dispatch routine for miniport drivers that support WMI.
old-location: storage\scsiportwmidispatchfunction.htm
old-project: storage
ms.assetid: 48806050-403b-4375-8b19-e867f905b761
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWmiDispatchFunction, ScsiPortWmiDispatchFunction routine [Storage Devices], scsiprt_03d0ec2c-b525-48d5-bcc3-cfd89fe020bd.xml, scsiwmi/ScsiPortWmiDispatchFunction, storage.scsiportwmidispatchfunction
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsiwmi.h
api_name:
-	ScsiPortWmiDispatchFunction
product:
- Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# ScsiPortWmiDispatchFunction function


## -description


The <b>ScsiPortWmiDispatchFunction</b> routine is a dispatch routine for miniport drivers that support WMI. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param WmiLibInfo [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565395">SCSI_WMILIB_CONTEXT</a> structure that contains registration information for a miniport driver's data blocks and event blocks and defines entry points for the miniport driver's WMI library callback routines.


### -param MinorFunction [in]

Indicates the WMI action to perform. The miniport driver sets <i>MinorFunction</i> to <b>Srb-&gt;WmiSubFunction</b> from the input SRB.


### -param DeviceContext [in]

Pointer to a miniport driver-defined context value. The port driver will pass <i>DeviceContext</i> to the miniport driver's <i>HwScsiWmiXxx</i> callback routine. This value would typically point to a HW_DEVICE_EXTENSION structure.


### -param RequestContext [in]

Pointer to a SCSIWMI_REQUEST_CONTEXT structure that contains context information for the WMI SRB. If the SRB can pend, the miniport driver must allocate this structure from the SRB extension because the request context must remain valid until after <b>ScsiPortWmiPostProcess</b> returns with the final SRB return status and buffer size. <b>ScsiPortWmiDispatchFunction </b>will pass <i>RequestContext</i> to the miniport driver's callback routine that processes this request.


### -param DataPath [in]

Pointer to a GUID that represents the data block associated with the request. The miniport driver sets <i>DataPath</i> to <b>Srb-&gt;DataPath</b> from the input SRB.


### -param BufferSize [in]

Specifies the size in bytes of the data buffer. The miniport driver sets <i>BufferSize</i> to <b>Srb-&gt;DataTransferLength</b> from the input SRB.


### -param Buffer [in]

Pointer to the data buffer. The miniport driver sets <i>Buffer</i> to <b>Srb-&gt;DataBuffer</b> from the input SRB.


## -returns



<b>ScsiPortWmiDispatchFunction</b> returns <b>TRUE</b> if the request is pending, or <b>FALSE</b> if the request was completed.




## -remarks



When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <b>ScsiPortWmiDispatchFunction</b> with request parameters, including a pointer to an initialized SCSI_WMILIB_CONTEXT structure. This structure contains information about the miniport driver's data blocks and event blocks and defines entry points for the miniport driver's <i>HwScsiWmiXxx</i> callback routines. 

<b>ScsiPortWmiDispatchFunction</b> confirms that the SRB is a WMI request and determines whether the block specified by the request is valid for the miniport driver. If these conditions are met, <b>ScsiPortWmiDispatchFunction</b> processes the SRB by calling the appropriate <i>HwScsiWmiXxx</i> entry point in the miniport driver's SCSI_WMILIB_CONTEXT structure. If the miniport driver does not define an entry point for an optional <i>HwScsiWmiXxx</i> routine, the port driver handles the request.

In either case, after <b>ScsiPortWmiDispatchFunction</b> returns, the miniport driver should do the following for requests that it does not pend:

<ul>
<li>
Set <b>Srb-&gt;DataTransferLength</b> to the value returned by <b>ScsiPortWmiGetReturnSize</b>

</li>
<li>
Set <b>Srb-&gt;SrbStatus</b> to the value returned by <b>ScsiPortWmiGetReturnStatus</b>

</li>
<li>
Call <b>ScsiPortNotification</b> with <b>RequestComplete</b> and again with <b>NextRequest</b>

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565395">SCSI_WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564789">ScsiPortWmiGetReturnSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>
 

 

