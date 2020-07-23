---
UID: NF:fwpsk.FwpsvSwitchNotifyComplete0
title: FwpsvSwitchNotifyComplete0 function (fwpsk.h)
description: The FwpsvSwitchNotifyComplete0 function completes a pending virtual switch event notification.Note  FwpsvSwitchNotifyComplete0 is a specific version of FwpsvSwitchNotifyComplete.
old-location: netvista\fwpsvswitchnotifycomplete0.htm
tech.root: netvista
ms.assetid: 5e40a31f-7730-48f0-899f-f59be654c991
ms.date: 05/02/2018
keywords: ["FwpsvSwitchNotifyComplete0 function"]
ms.keywords: FwpsvSwitchNotifyComplete0, FwpsvSwitchNotifyComplete0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsvSwitchNotifyComplete0, netvista.fwpsvswitchnotifycomplete0
f1_keywords:
 - "fwpsk/FwpsvSwitchNotifyComplete0"
 - "FwpsvSwitchNotifyComplete0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsvSwitchNotifyComplete0
targetos: Windows
req.typenames: 
---

# FwpsvSwitchNotifyComplete0 function


## -description


The <b>FwpsvSwitchNotifyComplete0</b> function completes a pending virtual switch event notification.<div class="alert"><b>Note</b>  <b>FwpsvSwitchNotifyComplete0</b> is a specific version of <b>FwpsvSwitchNotifyComplete</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param completionContext

The context data that was  passed to the callback driver from the virtual switch event notify function.


### -param status

Any NTSTATUS value that is a valid return code for the notification that was pending completion except for STATUS_PENDING.


### -param flags

Reserved. Set this member to zero.


### -param reserved

Reserved. Set this member to zero.


## -remarks




    If a callout driver returns STATUS_PENDING from a WFP notification function, WFP will return STATUS_PENDING for any associated OID request. The callout  driver calls the <b>FwpsvSwitchNotifyComplete0</b> function to complete the pending operation. After the <b>FwpsvSwitchNotifyComplete0</b> call, WFP calls the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequestcomplete">NdisFOidRequestComplete</a> function to complete the OID for  the virtual switch.
   




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequestcomplete">NdisFOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

