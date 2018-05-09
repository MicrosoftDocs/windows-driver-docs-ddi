---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSaveBegin
title: VmbChannelSaveBegin function
author: windows-driver-content
description: The VmbChannelSaveBegin function initializes the context for saving the state of a channel. The driver must check the return value of the function.
old-location: netvista\vmbchannelsavebegin.htm
old-project: netvista
ms.assetid: A0946287-3ED2-4DE1-A3D7-46611B25BB93
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbChannelSaveBegin, VmbChannelSaveBegin function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsavebegin, vmbuskernelmodeclientlibapi/VmbChannelSaveBegin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
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
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbChannelSaveBegin
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbChannelSaveBegin function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSaveBegin</b> function initializes the context for saving the state of a channel. The driver must check the return value of the function.


## -parameters




### -param Channel [in]

A handle for the channel to save.  


## -returns



<b>VmbChannelSaveBegin</b> returns a status code.




## -remarks



The
caller next calls the <a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a> function multiple times until
all the state is saved, and then calls the <a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a> function.




## -see-also




<a href="https://msdn.microsoft.com/57266CAE-C069-4379-92FD-0F93FECC6EB5"> VmbChannelSaveContinue</a>



<a href="https://msdn.microsoft.com/0E61AF98-DC71-4234-B337-71B2AF65D858">VmbChannelSaveEnd</a>
 

 

