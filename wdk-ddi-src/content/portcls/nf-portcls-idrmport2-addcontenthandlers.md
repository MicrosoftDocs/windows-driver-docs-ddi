---
UID: NF:portcls.IDrmPort2.AddContentHandlers
title: IDrmPort2::AddContentHandlers method
author: windows-driver-content
description: The AddContentHandlers method provides the system with a list of functions that handle protected content.
old-location: audio\idrmport2_addcontenthandlers.htm
old-project: audio
ms.assetid: b65608f4-de9a-4bed-a966-586e50c50e45
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: AddContentHandlers method [Audio Devices], IDrmPort2 interface, AddContentHandlers, IDrmPort2::AddContentHandlers, portcls/IDrmPort2::AddContentHandlers, AddContentHandlers method [Audio Devices], IDrmPort2 interface [Audio Devices], AddContentHandlers method, audio.idrmport2_addcontenthandlers, IDrmPort2, audmp-routines_f2bbb2e7-eed1-4ffd-93d9-050dcb6b0b60.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	portcls.h
apiname: 
-	IDrmPort2.AddContentHandlers
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDrmPort2::AddContentHandlers method


## -description


The <code>AddContentHandlers</code> method provides the system with a list of functions that handle protected content. Note that this method is identical in operation to the <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a> function, and its parameter definitions and return value are also identical.


## -syntax


````
NTSTATUS AddContentHandlers();
````


## -parameters




### -param ContentId




### -param paHandlers




### -param NumHandlers





## -returns


See return value definition in <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>.



## -remarks


See comments in <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>.



## -see-also

<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>

<a href="..\portcls\nn-portcls-idrmport2.md">IDrmPort2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IDrmPort2::AddContentHandlers method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

