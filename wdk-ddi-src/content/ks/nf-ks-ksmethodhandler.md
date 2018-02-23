---
UID: NF:ks.KsMethodHandler
title: KsMethodHandler function
author: windows-driver-content
description: The KsMethodHandler function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL.
old-location: stream\ksmethodhandler.htm
old-project: stream
ms.assetid: 730b5fae-3536-44ed-8f92-e4563a137be9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KsMethodHandler function [Streaming Media Devices], ks/KsMethodHandler, ksfunc_1f1959ed-e370-4ebb-9932-435c448a944b.xml, stream.ksmethodhandler, KsMethodHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsMethodHandler
product: Windows
targetos: Windows
req.typenames: 
---

# KsMethodHandler function


## -description


The <b>KsMethodHandler</b> function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL.


## -syntax


````
NTSTATUS KsMethodHandler(
  _In_       PIRP         Irp,
  _In_       ULONG        MethodSetsCount,
  _In_ const KSMETHOD_SET *MethodSet
);
````


## -parameters




### -param Irp [in]

Specifies the IRP with the method request being handled.


### -param MethodSetsCount [in]

Indicates the number of method set structures being passed.


### -param MethodSet [in]

Specifies the pointer to the list of method set information.


## -returns



The <b>KsMethodHandler</b> function returns STATUS_SUCCESS if successful, or an error specific to the method being handled if unsuccessful. The function always sets the IO_STATUS_BLOCK.Information field of the PIRP.IoStatus element within the IRP to zero because of an internal error, unless the element is set by a method handler. The function does not set the IO_STATUS_BLOCK.Status field nor complete the IRP.




## -remarks



The owner of a method set can perform prefiltering or postfiltering of the method handling using the <b>KsMethodHandler</b> and <b>KsFastMethodHandler </b>functions.




## -see-also

<a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>



<a href="..\ks\nf-ks-ksfastmethodhandler.md">KsFastMethodHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsMethodHandler function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

