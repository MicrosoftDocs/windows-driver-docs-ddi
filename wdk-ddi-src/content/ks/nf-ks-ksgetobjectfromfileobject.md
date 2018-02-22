---
UID: NF:ks.KsGetObjectFromFileObject
title: KsGetObjectFromFileObject function
author: windows-driver-content
description: The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject.
old-location: stream\ksgetobjectfromfileobject.htm
old-project: stream
ms.assetid: 6bd4f75b-a332-4e1f-8df7-0d6f51b0737b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KsGetObjectFromFileObject, KsGetObjectFromFileObject, stream.ksgetobjectfromfileobject, avfunc_800add7f-a220-4ad8-92bd-57e102739c8d.xml, KsGetObjectFromFileObject function [Streaming Media Devices]
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
-	KsGetObjectFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectFromFileObject function


## -description


The<b> KsGetObjectFromFileObject</b> function returns the AVStream object cast to PVOID from <i>FileObject</i>.


## -syntax


````
PVOID KsGetObjectFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which to determine the associated AVStream object.


## -returns



<b>KsGetObjectFromFileObject</b> returns a pointer to the AVStream object associated with <i>FileObject</i> (cast to PVOID). This pointer may point to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> or a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>, for example.




## -see-also

<a href="..\ks\nf-ks-ksgetfilterfromfileobject.md">KsGetFilterFromFileObject</a>



<a href="..\ks\nf-ks-kspingetconnectedpinfileobject.md">KsPinGetConnectedPinFileObject</a>



<a href="..\ks\nf-ks-ksgetpinfromfileobject.md">KsGetPinFromFileObject</a>



<a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetObjectFromFileObject function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

