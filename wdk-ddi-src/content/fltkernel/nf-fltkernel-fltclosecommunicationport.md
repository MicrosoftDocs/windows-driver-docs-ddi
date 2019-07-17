---
UID: NF:fltkernel.FltCloseCommunicationPort
title: FltCloseCommunicationPort function (fltkernel.h)
description: FltCloseCommunicationPort closes a minifilter driver's communication server port.
old-location: ifsk\fltclosecommunicationport.htm
tech.root: ifsk
ms.assetid: e3ab0d74-2c97-43da-8bee-82caa3d91c98
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_d55f3e54-9c1c-4fd0-92e6-1e950c2a4637.xml, FltCloseCommunicationPort, FltCloseCommunicationPort function [Installable File System Drivers], fltkernel/FltCloseCommunicationPort, ifsk.fltclosecommunicationport
ms.topic: function
f1_keywords:
 - "fltkernel/FltCloseCommunicationPort"
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
- FltCloseCommunicationPort
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCloseCommunicationPort function


## -description


<b>FltCloseCommunicationPort</b> closes a minifilter driver's communication server port. 


## -parameters




### -param ServerPort [in]

Opaque port handle for the server port to be closed. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



<b>FltCloseCommunicationPort</b> closes a communication server port that was created by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatecommunicationport">FltCreateCommunicationPort</a>. 

A minifilter driver normally calls <b>FltCloseCommunicationPort</b> from its <i>FilterUnloadCallback</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_filter_unload_callback">PFLT_FILTER_UNLOAD_CALLBACK</a>) routine. 

After <b>FltCloseCommunicationPort</b> is called, the opaque port handle specified by the <i>ServerPort</i> parameter is no longer valid and cannot safely be used. (The <i>ServerPort</i> handle is for the communication server port that the minifilter driver uses to listen for incoming connections.) 

When the communication server port is closed, existing connections are not affected. However, no more incoming connections will be accepted. 

This routine closes handle for the minifilter driver's server port, which listens for incoming connections. To disconnect a specific connection from the minifilter driver, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcloseclientport">FltCloseClientPort</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filterconnectcommunicationport">FilterConnectCommunicationPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcloseclientport">FltCloseClientPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatecommunicationport">FltCreateCommunicationPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsendmessage">FltSendMessage</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_filter_unload_callback">PFLT_FILTER_UNLOAD_CALLBACK</a>
 

 

