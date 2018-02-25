---
UID: NS:avc._AVC_SETCONNECT_INFO
title: "_AVC_SETCONNECT_INFO"
author: windows-driver-content
description: The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.
old-location: stream\avc_setconnect_info.htm
old-project: stream
ms.assetid: 16672908-6f1f-471b-b82e-d548e3efeb20
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PAVC_SETCONNECT_INFO, ,, A, AVC_SETCONNECT_INFO, AVC_SETCONNECT_INFO structure [Streaming Media Devices], C, E, F, I, N, O, P, PAVC_SETCONNECT_INFO, PAVC_SETCONNECT_INFO structure pointer [Streaming Media Devices], S, T, V, _, _AVC_SETCONNECT_INFO, avc/AVC_SETCONNECT_INFO, avc/PAVC_SETCONNECT_INFO, avcref_eec9cff7-6ae3-49d3-a649-349b8284630b.xml, stream.avc_setconnect_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avc.h
req.include-header: Avc.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	AVC_SETCONNECT_INFO
product: Windows
targetos: Windows
req.typenames: AVC_SETCONNECT_INFO, *PAVC_SETCONNECT_INFO
---

# _AVC_SETCONNECT_INFO structure


## -description


The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections.


## -syntax


````
typedef struct _AVC_SETCONNECT_INFO {
  ULONG          PinId;
  AVCCONNECTINFO ConnectInfo;
} AVC_SETCONNECT_INFO, *PAVC_SETCONNECT_INFO;
````


## -struct-fields




### -field PinId

Specifies the offset (or ID) of the pin for which information is to be set.


### -field ConnectInfo

The AVCCONNECTINFO values for the specified pin.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also

<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554171">AVC_FUNCTION_SET_CONNECTINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_SETCONNECT_INFO structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

