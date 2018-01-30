---
UID: NF:ks.KsMapModuleName
title: KsMapModuleName function
author: windows-driver-content
description: The KsMapModuleName function returns the image name and resource identifier that corresponds to the PhysicalDeviceObject and ModuleName parameters.
old-location: stream\ksmapmodulename.htm
old-project: stream
ms.assetid: 3223a1bb-ab6c-45d7-9f9a-367a3aa7d465
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsMapModuleName, ksfunc_76aec7fa-5e31-46d7-b94d-d7bccac7c3cd.xml, KsMapModuleName function [Streaming Media Devices], KsMapModuleName, stream.ksmapmodulename
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
-	KsMapModuleName
product: Windows
targetos: Windows
req.typenames: 
---

# KsMapModuleName function


## -description


The <b>KsMapModuleName</b> function returns the image name and resource identifier that corresponds to the <i>PhysicalDeviceObject </i>and<i> ModuleName </i>parameters. 


## -syntax


````
NTSTATUS KsMapModuleName(
  _In_  PDEVICE_OBJECT  PhysicalDeviceObject,
  _In_  PUNICODE_STRING ModuleName,
  _Out_ PUNICODE_STRING ImageName,
  _Out_ PULONG_PTR      ResourceId,
  _Out_ PULONG          ValueType
);
````


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to a DEVICE_OBJECT for which to return the requested information.


### -param ModuleName [in]

Pointer to a buffer that contains the module name for which to return the requested information.


### -param ImageName [out]

A caller-allocated buffer that receives the image name for the specified resource.


### -param ResourceId [out]

Pointer to a caller-supplied variable that receives the resource identifier.


### -param ValueType [out]

Pointer to a location into which the function returns the value type of the specified resource.


## -returns


<b>KsMapModuleName</b> returns STATUS_SUCCESS if the requested values are found; otherwise, the routine returns an error code.



## -see-also

<a href="..\ks\nf-ks-ksgetimagenameandresourceid.md">KsGetImageNameAndResourceId</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsMapModuleName function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

