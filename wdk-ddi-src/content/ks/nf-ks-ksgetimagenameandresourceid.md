---
UID: NF:ks.KsGetImageNameAndResourceId
title: KsGetImageNameAndResourceId function
author: windows-driver-content
description: The KsGetImageNameAndResourceId function returns the image name and resource identifier that corresponds to the RegKey handle.
old-location: stream\ksgetimagenameandresourceid.htm
old-project: stream
ms.assetid: e73c885c-94e2-42cf-ace6-1b7b62aa33f5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksgetimagenameandresourceid, ksfunc_b4a55bde-4bbb-494e-969c-924547251e1d.xml, KsGetImageNameAndResourceId, KsGetImageNameAndResourceId function [Streaming Media Devices], ks/KsGetImageNameAndResourceId
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
-	KsGetImageNameAndResourceId
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetImageNameAndResourceId function


## -description


The <b>KsGetImageNameAndResourceId</b> function returns the image name and resource identifier that corresponds to the <i>RegKey </i>handle. 


## -syntax


````
NTSTATUS KsGetImageNameAndResourceId(
  _In_  HANDLE          RegKey,
  _Out_ PUNICODE_STRING ImageName,
  _Out_ PULONG_PTR      ResourceId,
  _Out_ PULONG          ValueType
);
````


## -parameters




### -param RegKey [in]

Specifies a handle for which to return the image name and resource identifier.


### -param ImageName [out]

A caller-allocated buffer that receives the image name for the specified resource.


### -param ResourceId [out]

Pointer to a caller-supplied variable that receives the resource identifier.


### -param ValueType [out]

Pointer to a location into which the function returns the value type of the specified resource.


## -returns



<b>KsGetImageNameAndResourceId</b> returns STATUS_SUCCESS if the requested values are found; otherwise, an error code is returned.




## -see-also

<a href="..\ks\nf-ks-ksmapmodulename.md">KsMapModuleName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetImageNameAndResourceId function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

