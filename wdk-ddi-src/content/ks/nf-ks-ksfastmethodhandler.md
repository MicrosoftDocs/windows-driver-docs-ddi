---
UID: NF:ks.KsFastMethodHandler
title: KsFastMethodHandler function (ks.h)
description: The KsFastMethodHandler function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksfastmethodhandler.htm
tech.root: stream
ms.assetid: 829e96e7-7063-4de3-b13a-0b0d12ba1f44
ms.date: 04/23/2018
ms.keywords: KsFastMethodHandler, KsFastMethodHandler function [Streaming Media Devices], ks/KsFastMethodHandler, ksfunc_4c9fb7a6-5297-4b74-a865-14a774f728a5.xml, stream.ksfastmethodhandler
f1_keywords:
 - "ks/KsFastMethodHandler"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsFastMethodHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFastMethodHandler function


## -description


The <b>KsFastMethodHandler</b> function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.


## -parameters




### -param FileObject [in]

Specifies the file object on which the request was made.


### -param Method [in]

Specifies the original method parameter. This will always be on FILE_LONG_ALIGNMENT, but may not be on FILE_QUAD_ALIGNMENT.


### -param MethodLength [in]

Specifies the length indicated by the caller of the method parameter.


### -param Data [in, out]

Specifies the original unaligned data parameter.


### -param DataLength [in]

Specifies the length indicated by the caller of the data parameter.


### -param IoStatus [out]

Specifies an aligned structure that is used to return error status and information.


### -param MethodSetsCount [in]

Indicates the number of method set structures being passed.


### -param MethodSet [in]

Specifies the pointer to the list of method set information.


## -returns



The <b>KsFastMethodHandler</b> function returns <b>TRUE</b> if the request is handled, or <b>FALSE</b> if the request is not handled. If the request is not handled, an IRP is generated. If the request was handled, the function sets the IoStatus->Information element to zero because of an internal error or the element is set by a method handler. The method handler also sets the IoStatus->Status field when the method is handled.




## -remarks



The owner of a method set can perform prefiltering or postfiltering of the method handling using the <b>KsFastMethodHandler</b> and <b>KsMethodHandler </b>functions. The <b>KsFastMethodHandler</b> function is used to process requests made through the fast I/O dispatch interface for Device Control. It is only used to process requests that can be fulfilled quickly. The <i>Wait</i> parameter of the fast I/O function is not passed and assumed to be <b>TRUE</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksmethodhandler">KsMethodHandler</a>
 

 

