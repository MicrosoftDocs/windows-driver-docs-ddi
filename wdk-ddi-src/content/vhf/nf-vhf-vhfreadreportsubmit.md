---
UID: NF:vhf.VhfReadReportSubmit
title: VhfReadReportSubmit function (vhf.h)
description: The HID source driver calls this method to submit a HID Read (Input) Report to Virtual HID Framework (VHF).
old-location: hid\vhfreadreportsubmit.htm
tech.root: hid
ms.assetid: DCC4EB4C-B9A0-4E25-B3BD-4CAB07022A7B
ms.date: 04/30/2018
keywords: ["VhfReadReportSubmit function"]
ms.keywords: VhfReadReportSubmit, VhfReadReportSubmit method [Human Input Devices], hid.vhfreadreportsubmit, vhf/VhfReadReportSubmit
f1_keywords:
 - "vhf/VhfReadReportSubmit"
 - "VhfReadReportSubmit"
req.header: vhf.h
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
req.lib: VhfKm.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- vhfKm.lib
- vhfKm.dll
api_name:
- VhfReadReportSubmit
targetos: Windows
req.typenames: 
---

# VhfReadReportSubmit function


## -description


The HID source driver calls this method to submit a HID Read (Input) Report to Virtual HID Framework (VHF).


## -parameters




### -param VhfHandle [in]

A handle to a virtual HID device that your HID source driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a>.


### -param HidTransferPacket [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet">HID_XFER_PACKET</a> structure that describes the HID report.


## -returns



If the <b>VhfReadReportSubmit</b> call succeeds, the method returns STATUS_SUCCESS. Otherwise an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS </a> value.




## -remarks



The HID source driver can choose to implement its buffering policy or let Virtual HID Framework (VHF) handle buffering. 

If the driver uses its own buffering policy, then it must implement and register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_ready_for_next_read_report">EvtVhfReadyForNextReadReport</a> callback function in its call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a>. It must call <i>VhfReadReportSubmit</i> only once after VHF has invoked <i>EvtVhfReadyForNextReadReport</i>. After the callback has been invoked, the driver can reuse the transfer buffer pointed to by <i>HidTransferPacket</i>. The driver must wait for the next time that VHF invokes <i>EvtVhfReadyForNextReadReport</i> before calling this method again. 

If the HID source driver does not implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nc-vhf-evt_vhf_ready_for_next_read_report">EvtVhfReadyForNextReadReport</a> callback, then there are no restrictions on calling this method. VHF uses the default buffering policy. The driver can reuse the transfer buffer after the call returns.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

