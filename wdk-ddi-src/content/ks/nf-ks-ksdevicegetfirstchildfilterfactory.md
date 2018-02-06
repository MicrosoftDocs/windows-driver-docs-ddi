---
UID: NF:ks.KsDeviceGetFirstChildFilterFactory
title: KsDeviceGetFirstChildFilterFactory function
author: windows-driver-content
description: The KsDeviceGetFirstChildFilterFactory function returns the first child filter factory belonging to a given AVStream device.
old-location: stream\ksdevicegetfirstchildfilterfactory.htm
old-project: stream
ms.assetid: af388fd1-c95b-42ae-9d18-5fb416c28bc1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksdevicegetfirstchildfilterfactory, KsDeviceGetFirstChildFilterFactory function [Streaming Media Devices], KsDeviceGetFirstChildFilterFactory, avfunc_99fdc67f-eca0-460d-b1fb-d9881bd6e4c9.xml, ks/KsDeviceGetFirstChildFilterFactory
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsDeviceGetFirstChildFilterFactory
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceGetFirstChildFilterFactory function


## -description


The<b> KsDeviceGetFirstChildFilterFactory</b> function returns the first child filter factory belonging to a given AVStream device.


## -syntax


````
PKSFILTERFACTORY __inline KsDeviceGetFirstChildFilterFactory(
  _In_ PKSDEVICE Device
);
````


## -parameters




### -param Device [in]

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device for which to find the first child filter factory.


## -returns


Returns a pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure representing the first child filter factory of <i>Device</i>. If there are no filter factories registered on <i>Device</i>, <b>NULL</b> is returned.



## -remarks


This call is an inline function call to <a href="..\ks\nf-ks-ksgetfirstchild.md">KsGetFirstChild</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

For a graphical representation of AVStream parent/child relationships, see the diagram in <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.



## -see-also

<a href="..\ks\nf-ks-ksgetfirstchild.md">KsGetFirstChild</a>

<a href="..\ks\nf-ks-ksfilterfactorygetnextsiblingfilterfactory.md">KsFilterFactoryGetNextSiblingFilterFactory</a>

<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeviceGetFirstChildFilterFactory function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

