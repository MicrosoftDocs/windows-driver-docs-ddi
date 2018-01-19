---
UID: NF:portcls.PcForwardContentToFileObject
title: PcForwardContentToFileObject function
author: windows-driver-content
description: The PcForwardContentToFileObject function is obsolete and is maintained only to support existing drivers.
old-location: audio\pcforwardcontenttofileobject.htm
old-project: audio
ms.assetid: 3cad8e61-e016-415a-9aa9-1169267dc729
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcForwardContentToFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToFileObject function in Microsoft Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcForwardContentToFileObject
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: 
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcForwardContentToFileObject function



## -description
The <b>PcForwardContentToFileObject</b> function is obsolete and is maintained only to support existing drivers. Note that this function call is identical in operation to the <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a> function, and its parameter definitions and return value are also identical.



## -syntax

````
PORTCLASSAPI NTSTATUS NTAPI  PcForwardContentToFileObject(void);
````


## -parameters


## -returns
See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>.

See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>.

See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>.


## -remarks
For more information, see the comments in <a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>.


## -see-also
<dl>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcForwardContentToFileObject function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

