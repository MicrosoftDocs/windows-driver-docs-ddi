---
UID: NF:ks.KsGetObjectTypeFromFileObject
title: KsGetObjectTypeFromFileObject function
author: windows-driver-content
description: The KsGetObjectTypeFromFileObject function returns the AVStream object type that is associated with a given file object.
old-location: stream\ksgetobjecttypefromfileobject.htm
old-project: stream
ms.assetid: b963cf53-68ea-49b6-bbda-a93216fb10a5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsGetObjectTypeFromFileObject, KsGetObjectTypeFromFileObject function [Streaming Media Devices], avfunc_51a9a4d6-1481-45f9-918e-582907e8513c.xml, KsGetObjectTypeFromFileObject, stream.ksgetobjecttypefromfileobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetObjectTypeFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectTypeFromFileObject function


## -description


The<b> KsGetObjectTypeFromFileObject </b>function returns the AVStream object type that is associated with a given file object.


## -syntax


````
KSOBJECTTYPE KsGetObjectTypeFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which to determine the associated AVStream object type.


## -returns



<b>KsGetObjectTypeFromFileObject</b> returns the object type of the AVStream object associated with <i>FileObject</i> as a <a href="..\ks\ne-ks-ksobjecttype.md">KSOBJECTTYPE</a> enumeration. This can be one of the following: <b>KsObjectTypeDevice</b>, <b>KsObjectTypeFilterFactory</b>, <b>KsObjectTypeFilter</b>, or <b>KsObjectTypePin</b>.




## -see-also

<a href="..\ks\nf-ks-kspingetconnectedpinfileobject.md">KsPinGetConnectedPinFileObject</a>



<a href="..\ks\nf-ks-ksgetfilterfromfileobject.md">KsGetFilterFromFileObject</a>



<a href="..\ks\nf-ks-ksgetpinfromfileobject.md">KsGetPinFromFileObject</a>



<a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetObjectTypeFromFileObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

