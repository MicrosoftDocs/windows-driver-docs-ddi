---
UID: NC:vhf.EVT_VHF_READY_FOR_NEXT_READ_REPORT
title: EVT_VHF_READY_FOR_NEXT_READ_REPORT
author: windows-driver-content
description: The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.
old-location: hid\evtvhfreadyfornextreadreport.htm
old-project: hid
ms.assetid: 02DDBE00-C342-474B-8D06-FBB929BA4760
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.evtvhfreadyfornextreadreport, EvtVhfReadyForNextReadReport callback function [Human Input Devices], EvtVhfReadyForNextReadReport, EVT_VHF_READY_FOR_NEXT_READ_REPORT, EVT_VHF_READY_FOR_NEXT_READ_REPORT, vhf/EvtVhfReadyForNextReadReport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	vhf.h
apiname:
-	EvtVhfReadyForNextReadReport
product: Windows
targetos: Windows
req.typenames: USB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR, *PUSB_SUPERSPEED_ENDPOINT_COMPANION_DESCRIPTOR
req.product: Windows 10 or later.
---

# EVT_VHF_READY_FOR_NEXT_READ_REPORT callback


## -description


The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF.


## -prototype


````
EVT_VHF_READY_FOR_NEXT_READ_REPORT EvtVhfReadyForNextReadReport;

void EvtVhfReadyForNextReadReport(
  _In_ PVOID VhfClientContext
)
{ ... }
````


## -parameters




### -param VhfClientContext [in]

Pointer to the HID source driver-defined context structure that the driver passed in the previous call to <a href="..\vhf\nf-vhf-vhfcreate.md">VhfCreate</a> to create the virtual HID device.


## -returns



This callback function does not return a value.




## -remarks



Virtual HID Framework (VHF) invokes this callback function to notify the HID source driver that it can submit a buffer to get the HID Input Report. After the callback is invoked, the HID source driver must call <a href="..\vhf\nf-vhf-vhfreadreportsubmit.md">VhfReadReportSubmit</a>  only once. If a portion of the HID Input Report is still pending, the driver must wait for VHF to invoke <i>EvtVhfReadyForNextReadReport</i> before the driver can call <b>VhfReadReportSubmit</b> again.

If the HID source driver does not implement this callback function, VHF uses a default buffering policy for HID Read (Input) Reports.




## -see-also

<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20EVT_VHF_READY_FOR_NEXT_READ_REPORT callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

