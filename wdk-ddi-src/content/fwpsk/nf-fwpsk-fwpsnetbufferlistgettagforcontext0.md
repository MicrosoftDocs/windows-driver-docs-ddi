---
UID: NF:fwpsk.FwpsNetBufferListGetTagForContext0
title: FwpsNetBufferListGetTagForContext0 function
author: windows-driver-content
description: The FwpsNetBufferListGetTagForContext0 function gets a locally unique context tag that can be used to associate packets with the callout driver.Note  FwpsNetBufferListGetTagForContext0 is a specific version of FwpsNetBufferListGetTagForContext.
old-location: netvista\fwpsnetbufferlistgettagforcontext0.htm
old-project: netvista
ms.assetid: f4b9b6ab-2251-4b8a-baf5-16c845a1a4db
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsNetBufferListGetTagForContext0, FwpsNetBufferListGetTagForContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListGetTagForContext0, netvista.fwpsnetbufferlistgettagforcontext0, wfp_ref_2_funct_3_fwps_J-Q_f81dda7b-70fb-42ae-8641-c9bb2a9e7982.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
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
-	FwpsNetBufferListGetTagForContext0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsNetBufferListGetTagForContext0 function


## -description


The <b>FwpsNetBufferListGetTagForContext0</b> function gets a locally unique context tag that can be used to
  associate packets with the callout driver.
<div class="alert"><b>Note</b>  <b>FwpsNetBufferListGetTagForContext0</b> is a specific version of <b>FwpsNetBufferListGetTagForContext</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters






## -returns



The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.




## -remarks



The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551191">FwpsNetBufferListAssociateContext0</a>.




## -see-also




<a href="https://msdn.microsoft.com/31135396-303b-4b94-8616-a4b7be207fa1">
   FwpsNetBufferListAssociateContext0</a>



<a href="https://msdn.microsoft.com/bd3aa1a2-3ff5-47e4-93f6-5cb2022ec630">
   FwpsNetBufferListRemoveContext0</a>



<a href="https://msdn.microsoft.com/482cec75-8a21-4988-b869-639d019f9460">
   FwpsNetBufferListRetrieveContext0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/a151256b-d69f-4abb-bf68-644f157dfdd7">Using Packet Tagging</a>
 

 

