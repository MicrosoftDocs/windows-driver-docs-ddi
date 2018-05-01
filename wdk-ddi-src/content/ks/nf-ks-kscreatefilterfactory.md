---
UID: NF:ks.KsCreateFilterFactory
title: KsCreateFilterFactory function
author: windows-driver-content
description: The KsCreateFilterFactory function adds a filter factory to a given device.
old-location: stream\kscreatefilterfactory.htm
old-project: stream
ms.assetid: ebfdae87-febc-4383-93f4-5d613df273a9
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsCreateFilterFactory, KsCreateFilterFactory function [Streaming Media Devices], avfunc_0867c824-52e2-475a-9f36-05e6fba4cdd9.xml, ks/KsCreateFilterFactory, stream.kscreatefilterfactory
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsCreateFilterFactory
product: Windows
targetos: Windows
req.typenames: 
---

# KsCreateFilterFactory function


## -description


The<b> KsCreateFilterFactory</b> function adds a filter factory to a given device.


## -parameters




### -param DeviceObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure for which to add a filter factory. 


### -param Descriptor [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a> that describes the characteristics of individual filters that this factory can create.


### -param RefString [in, optional]

If this argument is provided, this string is used as the reference string for filters created by this factory. Otherwise, the reference GUID provided in the descriptor is used.


### -param SecurityDescriptor [in, optional]

The security descriptor to use in creation of filters by this filter factory. If <b>NULL</b>, no descriptor is provided.


### -param CreateItemFlags [in]

The following table lists the flags that the minidriver writer uses to specify the characteristics of filters that the new filter factory can create. Set this parameter to the bitwise OR of the flags below.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSCREATE_ITEM_SECURITY_CHANGED

</td>
<td>
Indicates that the security descriptor on this object type has been changed and should be persisted.

</td>
</tr>
<tr>
<td>
KSCREATE_ITEM_WILDCARD

</td>
<td>
Indicates that this create item represents a wildcard that is used for any create requests that do not match any other create items. The ordering of the wildcard entry in the list of create items is irrelevant. Only a single wildcard entry is valid on any list of create items.

</td>
</tr>
<tr>
<td>
KSCREATE_ITEM_NOPARAMETERS

</td>
<td>
Indicates that this create item does not allow any parameters to be passed, and fails if any are found. (Normally, create parameters are passed on to the create handler.) This flag cannot be used with a wildcard flag.

</td>
</tr>
<tr>
<td>
KSCREATE_ITEM_FREEONSTOP

</td>
<td>
Indicates that the create item should be freed when the PnP manager sends <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>. Note that AVStream automatically frees such create items when the device receives PnP stop (<i>after</i> the client has received the PnP stop notification).

</td>
</tr>
</table>
 


### -param SleepCallback [in, optional]

A pointer to a minidriver-provided routine that receives notifications that the device associated with this filter is going to sleep. Prototype the routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void SleepCallback (IN PKSFILTERFACTORY FilterFactory,
    IN DEVICE_POWER_STATE State);</pre>
</td>
</tr>
</table></span></div>
If this parameter is <b>NULL</b>, this filter factory is not notified that the device is going to sleep. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>.


### -param WakeCallback [in, optional]

A pointer to a minidriver-provided routine that receives notifications that the device associated with this filter is waking up. Prototype the routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  void WakeCallback (IN PKSFILTERFACTORY FilterFactory,
    IN DEVICE_POWER_STATE State);</pre>
</td>
</tr>
</table></span></div>
If this parameter is <b>NULL</b>, this filter factory is not notified that the device is waking up. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">Device Power States</a>. 


### -param FilterFactory [out, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> structure that AVStream sets to point to the newly created filter factory object. If this optional parameter is unspecified, the caller is not informed about the resulting filter factory object.


## -returns



Returns STATUS_SUCCESS if the filter factory can be created. Otherwise, it returns an appropriate error code.




## -remarks



If you call <b>KsCreateFilterFactory</b> after <a href="https://msdn.microsoft.com/library/windows/hardware/ff554284">AVStrMiniDevicePostStart</a>), you must then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff562539">KsFilterFactorySetDeviceClassesState</a> to enable the device class. (Also call <b>KsFilterFactorySetDeviceClassesState</b> to disable a filter factory.)

If you call <b>KsCreateFilterFactory</b> in the context of <i>AVStrMiniDevicePostStart</i> or before, you do not need to do this.

Before calling this function, the minidriver must obtain the device mutex. For information about how to do this, see <a href="https://msdn.microsoft.com/cec2a040-59d6-44ef-aef1-04f434811d60">Device Mutex in AVStream</a>.

This function should be used by minidrivers that either initialize themselves without a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562683">KsInitializeDriver</a> or that must dynamically add and remove new filter types. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562553">KSFILTER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563473">KSNODE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563534">KSPIN_DESCRIPTOR_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561675">KsDeleteFilterFactory</a>
 

 

