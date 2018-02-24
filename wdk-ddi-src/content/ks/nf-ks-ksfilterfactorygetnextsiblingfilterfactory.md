---
UID: NF:ks.KsFilterFactoryGetNextSiblingFilterFactory
title: KsFilterFactoryGetNextSiblingFilterFactory function
author: windows-driver-content
description: The KsFilterFactoryGetNextSiblingFilterFactory function returns the next filter factory belonging to the parent device of FilterFactory.
old-location: stream\ksfilterfactorygetnextsiblingfilterfactory.htm
old-project: stream
ms.assetid: e397d36c-3f28-4a70-9b4a-f13be094d47b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsFilterFactoryGetNextSiblingFilterFactory function [Streaming Media Devices], avfunc_b1bdc37b-de4a-4cfb-b1e9-1201225c29ab.xml, ks/KsFilterFactoryGetNextSiblingFilterFactory, KsFilterFactoryGetNextSiblingFilterFactory, stream.ksfilterfactorygetnextsiblingfilterfactory
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
-	KsFilterFactoryGetNextSiblingFilterFactory
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetNextSiblingFilterFactory function


## -description


The<b> KsFilterFactoryGetNextSiblingFilterFactory</b> function returns the next filter factory belonging to the parent device of <i>FilterFactory</i>.


## -syntax


````
PKSFILTERFACTORY __inline KsFilterFactoryGetNextSiblingFilterFactory(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters




### -param FilterFactory [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> for which to return the next filter factory of its parent device.


## -returns



<b>KsFilterFactoryGetNextSiblingFilterFactory</b> returns a pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure that represents the next sibling filter factory of <i>FilterFactory</i>. If no such filter factory exists, <b>NULL</b> is returned.




## -remarks



This call is an inline function call to <a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksdevicegetfirstchildfilterfactory.md">KsDeviceGetFirstChildFilterFactory</a>



<a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>



<a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetNextSiblingFilterFactory function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

