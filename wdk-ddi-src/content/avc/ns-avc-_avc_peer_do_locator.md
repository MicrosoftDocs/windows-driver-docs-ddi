---
UID: NS:avc._AVC_PEER_DO_LOCATOR
title: "_AVC_PEER_DO_LOCATOR"
author: windows-driver-content
description: The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of avc.sys.
old-location: stream\avc_peer_do_locator.htm
old-project: stream
ms.assetid: a1ef8626-1920-422b-a0ed-4da9ac495f74
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PAVC_PEER_DO_LOCATOR structure pointer [Streaming Media Devices], AVC_PEER_DO_LOCATOR, *PAVC_PEER_DO_LOCATOR, avc/AVC_PEER_DO_LOCATOR, PAVC_PEER_DO_LOCATOR, avc/PAVC_PEER_DO_LOCATOR, avcref_6e8543dc-a712-4031-8f48-cf789d320551.xml, _AVC_PEER_DO_LOCATOR, stream.avc_peer_do_locator, AVC_PEER_DO_LOCATOR structure [Streaming Media Devices]
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
-	AVC_PEER_DO_LOCATOR
product: Windows
targetos: Windows
req.typenames: "*PAVC_PEER_DO_LOCATOR, AVC_PEER_DO_LOCATOR"
---

# _AVC_PEER_DO_LOCATOR structure


## -description


The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of <i>avc.sys</i>.


## -syntax


````
typedef struct _AVC_PEER_DO_LOCATOR {
  NODE_ADDRESS   NodeAddress;
  ULONG          Generation;
  PDEVICE_OBJECT DeviceObject;
} AVC_PEER_DO_LOCATOR, *PAVC_PEER_DO_LOCATOR;
````


## -struct-fields




### -field NodeAddress

Set to the NodeAddress of the device whose driver instance is to be located.


### -field Generation

Set to the Generation obtained with the NodeAddress.


### -field DeviceObject

On success, points to the FDO of the <i>avc.sys</i> instance. The caller must release the reference to this object (by using <b>ObDereferenceObject</b>) when finished with it.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://msdn.microsoft.com/3b4ec139-ff01-40bd-8e29-92f554180585">How to Use Avc.sys</a> For information about building and sending an AV/C command.




## -see-also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="..\avc\ns-avc-_avc_multifunc_irb.md">AVC_MULTIFUNC_IRB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554152">AVC_FUNCTION_FIND_PEER_DO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_PEER_DO_LOCATOR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

