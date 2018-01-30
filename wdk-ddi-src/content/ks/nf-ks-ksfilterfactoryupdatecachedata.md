---
UID: NF:ks.KsFilterFactoryUpdateCacheData
title: KsFilterFactoryUpdateCacheData function
author: windows-driver-content
description: The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.
old-location: stream\ksfilterfactoryupdatecachedata.htm
old-project: stream
ms.assetid: a5c868a5-0e79-482b-9694-02cae2de99ca
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterFactoryUpdateCacheData, avfunc_2fdbd12c-b074-415e-8de3-bfbe61ef198a.xml, stream.ksfilterfactoryupdatecachedata, KsFilterFactoryUpdateCacheData function [Streaming Media Devices], KsFilterFactoryUpdateCacheData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 9.0 and later DirectX versions.
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
-	KsFilterFactoryUpdateCacheData
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryUpdateCacheData function


## -description


The <b>KsFilterFactoryUpdateCacheData</b> function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory.


## -syntax


````
NTSTATUS KsFilterFactoryUpdateCacheData(
  _In_           PKSFILTERFACTORY    FilterFactory,
  _In_opt_ const KSFILTER_DESCRIPTOR *FilterDescriptor
);
````


## -parameters




### -param FilterFactory [in]

The <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> for which to update FilterData and Medium cache in the registry.


### -param FilterDescriptor [in, optional]

An optional <a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a> for which the FilterData key and Medium cache will be updated. If <b>NULL</b>, <i>FilterFactory</i>'s descriptor is used instead. Provide if the filter factory uses dynamic pins and needs to update information for pins that have not yet been instantiated.


## -returns


<b>
             KsFilterFactoryUpdateCacheData</b> returns STATUS_SUCCESS or a failure code, indicating whether the relevant registry information was successfully updated. It returns STATUS_INVALID_PARAMETER if no device interface is found that corresponds to the categories passed in the filter descriptor.



## -remarks


This function updates the FilterData key and Medium cache for all categories specified in <i>FilterDescriptor</i>. If <i>FilterDescriptor</i> is <b>NULL</b>, the FilterData and Medium cache are updated for all categories specified in <i>FilterFactory</i>'s <a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a> member.


<a href="..\ks\nf-ks-ksregisterfilterwithnokspins.md">KsRegisterFilterWithNoKSPins</a> provides similar functionality, but should not be used if two instances of <a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a> under the same <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> are registered in the same category, and differ only in reference GUID. In this case, <b>KsRegisterFilterWithNoKSPins</b> updates data only for the first, even though the second may have been specified.

Do not use this routine in place of <b>KsRegisterFilterWithNoKSPins</b> for filters with no KS pins, such as analog style crossbars. Use this routine only for a specific filter for which the minidriver is passing the corresponding filter factory.

In addition, <b>KsRegisterFilterWithNoKSPins</b> only allows one medium per registered pin. This may not be sufficient for a BDA minidriver.

For more information, see <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.
<div class="alert"><b>Note</b>  The <b>KsFilterFactoryUpdateCacheData</b> function can only be called in PASSIVE_LEVEL.</div><div> </div>


## -see-also

<a href="..\ks\nf-ks-ksregisterfilterwithnokspins.md">KsRegisterFilterWithNoKSPins</a>

<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>

<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryUpdateCacheData function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

