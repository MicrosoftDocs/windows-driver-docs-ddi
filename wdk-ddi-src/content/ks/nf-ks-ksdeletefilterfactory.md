---
UID: NF:ks.KsDeleteFilterFactory
title: KsDeleteFilterFactory macro
author: windows-driver-content
description: KsDeleteFilterFactory deletes a given filter factory.
old-location: stream\ksdeletefilterfactory.htm
old-project: stream
ms.assetid: 4d946524-8ad2-45a0-91be-861b30b0c297
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsDeleteFilterFactory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDeleteFilterFactory
req.alt-loc: Ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: 
---

# KsDeleteFilterFactory macro



## -description
<b>KsDeleteFilterFactory</b> deletes a given filter factory.



## -syntax

````
NTSTATUS KsDeleteFilterFactory(
  _In_ PKSFILTERFACTORY FilterFactory
);
````


## -parameters

### -param FilterFactory [in]

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure that represents the filter factory to be deleted.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kscreatefilterfactory.md">KsCreateFilterFactory</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfilterfactoryaddcreateitem.md">KsFilterFactoryAddCreateItem</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfilterfactorysetdeviceclassesstate.md">KsFilterFactorySetDeviceClassesState</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDeleteFilterFactory function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

