---
UID: NC:vhf.EVT_VHF_READY_FOR_NEXT_READ_REPORT
title: EVT_VHF_READY_FOR_NEXT_READ_REPORT (vhf.h)
description: The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.
old-location: hid\evtvhfreadyfornextreadreport.htm
tech.root: hid
ms.assetid: 02DDBE00-C342-474B-8D06-FBB929BA4760
ms.date: 04/30/2018
keywords: ["EVT_VHF_READY_FOR_NEXT_READ_REPORT callback function"]
ms.keywords: EVT_VHF_READY_FOR_NEXT_READ_REPORT, EVT_VHF_READY_FOR_NEXT_READ_REPORT callback, EvtVhfReadyForNextReadReport, EvtVhfReadyForNextReadReport callback function [Human Input Devices], hid.evtvhfreadyfornextreadreport, vhf/EvtVhfReadyForNextReadReport
f1_keywords:
 - "vhf/EvtVhfReadyForNextReadReport"
 - "EvtVhfReadyForNextReadReport"
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- vhf.h
api_name:
- EvtVhfReadyForNextReadReport
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VHF_READY_FOR_NEXT_READ_REPORT callback function


## -description


The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.


## -parameters




### -param VhfClientContext [in]

Pointer to the HID source driver-defined context structure that the driver passed in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfcreate">VhfCreate</a> to create the virtual HID device.


## -remarks



Virtual HID Framework (VHF) invokes this callback function to notify the HID source driver that it can submit a buffer to get the HID Input Report. After the callback is invoked, the HID source driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vhf/nf-vhf-vhfreadreportsubmit">VhfReadReportSubmit</a>  only once. If a portion of the HID Input Report is still pending, the driver must wait for VHF to invoke <i>EvtVhfReadyForNextReadReport</i> before the driver can call <b>VhfReadReportSubmit</b> again.

If the HID source driver does not implement this callback function, VHF uses a default buffering policy for HID Read (Input) Reports.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/hid/virtual-hid-framework--vhf-">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

