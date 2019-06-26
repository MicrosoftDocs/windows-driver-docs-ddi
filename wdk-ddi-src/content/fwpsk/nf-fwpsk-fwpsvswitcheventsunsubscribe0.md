---
UID: NF:fwpsk.FwpsvSwitchEventsUnsubscribe0
title: FwpsvSwitchEventsUnsubscribe0 function (fwpsk.h)
description: The FwpsvSwitchEventsUnsubscribe0 function releases resources that are associated with virtual switch notification subscriptions.Note  FwpsvSwitchEventsUnsubscribe0 is a specific version of FwpsvSwitchEventsUnsubscribe.
old-location: netvista\fwpsvswitcheventsunsubscribe0.htm
tech.root: netvista
ms.assetid: f83c6834-0438-42b8-ad9f-a1d82fcf361c
ms.date: 05/02/2018
ms.keywords: FwpsvSwitchEventsUnsubscribe0, FwpsvSwitchEventsUnsubscribe0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsvSwitchEventsUnsubscribe0, netvista.fwpsvswitcheventsunsubscribe0
ms.topic: function
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsvSwitchEventsUnsubscribe0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsvSwitchEventsUnsubscribe0 function


## -description


The <b>FwpsvSwitchEventsUnsubscribe0</b> function releases resources that are associated with virtual switch notification subscriptions.<div class="alert"><b>Note</b>  <b>FwpsvSwitchEventsUnsubscribe0</b> is a specific version of <b>FwpsvSwitchEventsUnsubscribe</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param subscriptionId

A unique event subscription identifier that the callout driver obtained by calling  the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a> function.




### -param flags

Reserved. Set this parameter to zero.


### -param reserved

Reserved. Set this parameter to  zero.


## -returns



None.




## -remarks




    A callout driver calls the <b>FwpsvSwitchEventsUnsubscribe0</b> function to unsubscribe to virtual switch notifications that the callout driver previously subscribed to  by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a> function. 


   




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsvswitcheventssubscribe0">FwpsvSwitchEventsSubscribe0</a>
 

 

