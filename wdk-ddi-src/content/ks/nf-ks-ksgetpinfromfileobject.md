---
UID: NF:ks.KsGetPinFromFileObject
title: KsGetPinFromFileObject function
author: windows-driver-content
description: The KsGetPinFromFileObject function returns the AVStream pin object associated with FileObject.
old-location: stream\ksgetpinfromfileobject.htm
old-project: stream
ms.assetid: 47e7fd44-b98f-4e0a-80c8-cc9b6dcc483b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: KsGetPinFromFileObject, avfunc_18bdc4eb-2823-481e-ba51-e4103ff10d8c.xml, ks/KsGetPinFromFileObject, KsGetPinFromFileObject function [Streaming Media Devices], stream.ksgetpinfromfileobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsGetPinFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetPinFromFileObject function


## -description


The<b> KsGetPinFromFileObject </b>function returns the AVStream pin object associated with <i>FileObject</i>.


## -syntax


````
PKSPIN __inline KsGetPinFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which to return the associated AVStream pin object.


## -returns



<b>KsGetPinFromFileObject</b> returns a pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure associated with <i>FileObject</i>.




## -remarks



The minidriver must verify that <i>FileObject</i> is a file object associated with an AVStream pin. Do this by calling <a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>.

This call is an inline call to <a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>. <b>KsGetPinFromFileObject </b>typecasts the return as a PKSPIN.




## -see-also

<a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>



<a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetPinFromFileObject function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

