---
UID: NF:scsiwmi.ScsiPortWmiGetReturnStatus
title: ScsiPortWmiGetReturnStatus macro
author: windows-driver-content
description: The ScsiPortWmiGetReturnStatus routine returns the status of a WMI SRB.
old-location: storage\scsiportwmigetreturnstatus.htm
old-project: storage
ms.assetid: 79213f47-ba4c-41b0-b095-1b5c25c79456
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ScsiPortWmiGetReturnStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: scsiwmi.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiPortWmiGetReturnStatus
req.alt-loc: scsiwmi.h
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
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# ScsiPortWmiGetReturnStatus macro



## -description
The <b>ScsiPortWmiGetReturnStatus</b> routine returns the status of a WMI SRB. 



## -syntax

````
UCHAR ScsiPortWmiGetReturnStatus(
   PSCSIWMI_REQUEST_CONTEXT RequestContext
);
````


## -parameters

### -param RequestContext 

Pointer to the request context for this SRB.


## -remarks
A miniport driver must call <b>ScsiPortWmiGetReturnStatus</b> to obtain the value to put into <b>Srb-&gt;SrbStatus</b>. <b>ScsiPortWmiGetReturnStatus</b> should be called sometime after the miniport driver calls <b>ScsiPortWmiPostProcess.</b>


## -see-also
<dl>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnstatus.md">ScsiPortWmiGetReturnStatus</a>
</dt>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>
</dt>
<dt>
<a href="..\scsiwmi\ns-scsiwmi-scsiwmi_request_context.md">SCSIWMI_REQUEST_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortWmiGetReturnStatus macro%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

