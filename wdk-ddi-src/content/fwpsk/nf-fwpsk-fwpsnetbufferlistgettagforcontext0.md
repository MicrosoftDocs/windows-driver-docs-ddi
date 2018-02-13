---
UID: NF:fwpsk.FwpsNetBufferListGetTagForContext0
title: FwpsNetBufferListGetTagForContext0 function
author: windows-driver-content
description: The FwpsNetBufferListGetTagForContext0 function gets a locally unique context tag that can be used to associate packets with the callout driver.Note  FwpsNetBufferListGetTagForContext0 is a specific version of FwpsNetBufferListGetTagForContext.
old-location: netvista\fwpsnetbufferlistgettagforcontext0.htm
old-project: netvista
ms.assetid: f4b9b6ab-2251-4b8a-baf5-16c845a1a4db
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FwpsNetBufferListGetTagForContext0, FwpsNetBufferListGetTagForContext0 function [Network Drivers Starting with Windows Vista], wfp_ref_2_funct_3_fwps_J-Q_f81dda7b-70fb-42ae-8641-c9bb2a9e7982.xml, fwpsk/FwpsNetBufferListGetTagForContext0, netvista.fwpsnetbufferlistgettagforcontext0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
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

## -syntax


````
UINT64 NTAPI FwpsNetBufferListGetTagForContext0(void);
````


## -parameters






## -returns



The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.




## -remarks



The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a>.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistretrievecontext0.md">
   FwpsNetBufferListRetrieveContext0</a>



<a href="https://msdn.microsoft.com/a151256b-d69f-4abb-bf68-644f157dfdd7">Using Packet Tagging</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistremovecontext0.md">
   FwpsNetBufferListRemoveContext0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">
   FwpsNetBufferListAssociateContext0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListGetTagForContext0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

