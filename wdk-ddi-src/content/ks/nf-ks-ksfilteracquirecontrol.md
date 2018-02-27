---
UID: NF:ks.KsFilterAcquireControl
title: KsFilterAcquireControl function
author: windows-driver-content
description: The KsFilterAcquireControl function acquires the filter control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilteracquirecontrol.htm
old-project: stream
ms.assetid: 93dfe9fe-e1af-45db-ab28-fd166f511fcc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterAcquireControl, KsFilterAcquireControl function [Streaming Media Devices], avfunc_63930ae0-491f-4916-a24f-7de5c8fa1ad3.xml, ks/KsFilterAcquireControl, stream.ksfilteracquirecontrol
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
-	KsFilterAcquireControl
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterAcquireControl function


## -description


The<b> KsFilterAcquireControl </b>function acquires the filter control mutex for the AVStream filter specified by <i>Filter</i>.


## -syntax


````
void __inline KsFilterAcquireControl(
  _In_ PKSFILTER Filter
);
````


## -parameters




### -param Filter [in]

The <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> for which to acquire the control mutex.


## -returns



None




## -remarks



This function is an inline call to <a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a> with the appropriate typecasting. Minidrivers that manipulate the filter control mutex should call this function instead of calling <b>KsAcquireControl </b>directly. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a>



<a href="..\ks\nf-ks-ksfilterreleasecontrol.md">KsFilterReleaseControl</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterAcquireControl function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

