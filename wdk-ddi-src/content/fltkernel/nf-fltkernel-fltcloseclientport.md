---
UID: NF:fltkernel.FltCloseClientPort
title: FltCloseClientPort function (fltkernel.h)
description: FltCloseClientPort closes a communication client port.
old-location: ifsk\fltcloseclientport.htm
tech.root: ifsk
ms.assetid: 7a23b8f6-688f-4aa4-9bf3-f8bda0458566
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_0def0996-8190-4482-a7bb-018c79773eca.xml, FltCloseClientPort, FltCloseClientPort function [Installable File System Drivers], fltkernel/FltCloseClientPort, ifsk.fltcloseclientport
f1_keywords:
 - "fltkernel/FltCloseClientPort"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltCloseClientPort
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCloseClientPort function


## -description


<b>FltCloseClientPort</b> closes a communication client port. 


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param ClientPort [out]

Pointer to a variable that contains the opaque port handle for the client port to be closed. On return, the variable receives <b>NULL</b>. This parameter is required and cannot be <b>NULL</b> on input. 


## -returns



None 




## -remarks



A minifilter driver normally calls <b>FltCloseClientPort</b> from the <i>DisconnectNotifyCallback</i> routine that it registered when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatecommunicationport">FltCreateCommunicationPort</a>. The Filter Manager calls the <i>DisconnectNotifyCallback</i> routine whenever the user-mode handle count for the client port reaches zero or when the minifilter driver is about to be unloaded. 

<b>FltCloseClientPort</b> closes a communication client port that was created by the minifilter driver's <i>ConnectNotifyCallback</i> routine. 

On input, the <i>ClientPort</i> parameter is a pointer to a variable containing the opaque handle for the client port to be closed. To ensure that any messages sent by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsendmessage">FltSendMessage</a> are synchronized properly when the communication client port is being closed, <b>FltCloseClientPort</b> sets this variable to <b>NULL</b>. 

This routine disconnects a specific connection from the minifilter driver. To close the handle for the minifilter driver's server port, which listens for incoming connections, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosecommunicationport">FltCloseCommunicationPort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterconnectcommunicationport">FilterConnectCommunicationPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclosecommunicationport">FltCloseCommunicationPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatecommunicationport">FltCreateCommunicationPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsendmessage">FltSendMessage</a>
 

 

