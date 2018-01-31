---
UID: NF:ks.KsFilterFactoryGetDevice
title: KsFilterFactoryGetDevice function
author: windows-driver-content
description: The KsFilterFactoryGetDevice function returns the AVStream device to which FilterFactory belongs.
old-location: stream\ksfilterfactorygetdevice.htm
old-project: stream
ms.assetid: e5b7b014-3e06-49f2-8ccd-45d74592e349
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterFactoryGetDevice, KsFilterFactoryGetDevice, KsFilterFactoryGetDevice function [Streaming Media Devices], stream.ksfilterfactorygetdevice, avfunc_1e2ec536-69a1-4606-9d99-ebdebd25c89a.xml
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
-	KsFilterFactoryGetDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetDevice function


## -description


The<b> KsFilterFactoryGetDevice </b>function returns the AVStream device to which <i>FilterFactory </i>belongs.


## -syntax


````
PKSDEVICE __inline KsFilterFactoryGetDevice(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters




#### - FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to find the corresponding AVStream device.


## -returns


Returns a pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device to which <i>FilterFactory</i> belongs.



## -remarks


This call is an inline function call to <a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>.

For more information about the AVStream object hierarchy, see  <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>.



## -see-also

<a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>

<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetDevice function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

