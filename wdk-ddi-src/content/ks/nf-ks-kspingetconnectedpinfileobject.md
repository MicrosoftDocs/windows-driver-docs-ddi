---
UID: NF:ks.KsPinGetConnectedPinFileObject
title: KsPinGetConnectedPinFileObject function
author: windows-driver-content
description: The KsPinGetConnectedPinFileObject function returns the file object for the pin to which Pin is connected. Works only for source pins.
old-location: stream\kspingetconnectedpinfileobject.htm
old-project: stream
ms.assetid: 1025c89f-8d63-4aeb-be7c-16b555cfa58a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_af97a9b7-4bf9-4faa-a728-099daf7d4c96.xml, stream.kspingetconnectedpinfileobject, ks/KsPinGetConnectedPinFileObject, KsPinGetConnectedPinFileObject function [Streaming Media Devices], KsPinGetConnectedPinFileObject
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsPinGetConnectedPinFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedPinFileObject function


## -description


The<b> KsPinGetConnectedPinFileObject </b>function returns the file object for the pin to which <i>Pin</i> is connected. Works only for source pins.


## -syntax


````
PFILE_OBJECT KsPinGetConnectedPinFileObject(
  _In_ PKSPIN Pin
);
````


## -parameters




### -param Pin [in]

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure that is the AVStream pin object for which to acquire the file object for the connected pin.


## -returns


If <i>Pin</i> is a source pin, <b>KsPinGetConnectedPinFileObject</b> returns a pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for the pin to which <i>Pin</i> is connected. If <i>Pin</i> is not a source pin, it returns <b>NULL</b>.



## -see-also

<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>

<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetConnectedPinFileObject function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

