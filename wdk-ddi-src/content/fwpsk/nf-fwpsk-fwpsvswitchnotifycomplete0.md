---
UID: NF:fwpsk.FwpsvSwitchNotifyComplete0
title: FwpsvSwitchNotifyComplete0 function
author: windows-driver-content
description: The FwpsvSwitchNotifyComplete0 function completes a pending virtual switch event notification.Note  FwpsvSwitchNotifyComplete0 is a specific version of FwpsvSwitchNotifyComplete.
old-location: netvista\fwpsvswitchnotifycomplete0.htm
old-project: netvista
ms.assetid: 5e40a31f-7730-48f0-899f-f59be654c991
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FwpsvSwitchNotifyComplete0, FwpsvSwitchNotifyComplete0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsvSwitchNotifyComplete0, netvista.fwpsvswitchnotifycomplete0
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsvSwitchNotifyComplete0
product: Windows
targetos: Windows
req.typenames: 
---

# FwpsvSwitchNotifyComplete0 function


## -description


The <b>FwpsvSwitchNotifyComplete0</b> function completes a pending virtual switch event notification.<div class="alert"><b>Note</b>  <b>FwpsvSwitchNotifyComplete0</b> is a specific version of <b>FwpsvSwitchNotifyComplete</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
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


## -returns



None.




## -remarks




    If a callout driver returns STATUS_PENDING from a WFP notification function, WFP will return STATUS_PENDING for any associated OID request. The callout  driver calls the <b>FwpsvSwitchNotifyComplete0</b> function to complete the pending operation. After the <b>FwpsvSwitchNotifyComplete0</b> call, WFP calls the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561833">NdisFOidRequestComplete</a> function to complete the OID for  the virtual switch.
   




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551150">FwpsCompleteClassify0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561833">NdisFOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

