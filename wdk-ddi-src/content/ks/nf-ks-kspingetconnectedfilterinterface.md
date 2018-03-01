---
UID: NF:ks.KsPinGetConnectedFilterInterface
title: KsPinGetConnectedFilterInterface function
author: windows-driver-content
description: The KsPinGetConnectedFilterInterface function queries the filter to which Pin is connected in order to obtain a pointer to a COM interface.
old-location: stream\kspingetconnectedfilterinterface.htm
old-project: stream
ms.assetid: 19fb7a3e-d795-4d5a-9f28-cfbf37dbcd96
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinGetConnectedFilterInterface, KsPinGetConnectedFilterInterface function [Streaming Media Devices], avfunc_d6f6f675-4d44-47c8-aa37-9ad533966603.xml, ks/KsPinGetConnectedFilterInterface, stream.kspingetconnectedfilterinterface
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
-	KsPinGetConnectedFilterInterface
product: Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedFilterInterface function


## -description


The<b> KsPinGetConnectedFilterInterface</b> function queries the filter to which <i>Pin</i> is connected in order to obtain a pointer to a COM interface.


## -syntax


````
NTSTATUS KsPinGetConnectedFilterInterface(
  _In_        PKSPIN Pin,
  _In_  const GUID   *InterfaceId,
  _Out_       PVOID  *Interface
);
````


## -parameters




### -param Pin [in]

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure. The filter to which this pin is attached is queried for the requested interface.


### -param InterfaceId [in]

A pointer to a GUID representing the interface ID for the interface to obtain. A <b>QueryInterface</b> call is automatically performed for this interface.


### -param Interface [out]

A pointer to a PVOID. As in COM, the resulting interface pointer is deposited into <i>*Interface</i>. This interface has a corresponding reference count and <i>must</i> be released by the caller as in COM.


## -returns



<b>KsPinGetConnectedFilterInterface</b> returns STATUS_SUCCESS if the interface exists on the connected filter or in the AVStream thunk. If STATUS_SUCCESS is returned, the interface pointer is deposited into <i>*Interface</i>. Otherwise, it returns STATUS_NOINTERFACE. Note that this corresponds to the COM HRESULT E_NOINTERFACE.




## -remarks



By default, objects support the <b>IUnknown</b> interface and the <a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a> interface. If the filter and connected pin are AVStream objects, the query and the returned interface pointer are direct calls to the other driver. However, if the connected pin and filter do not belong to an AVStream driver, a thunk is created that provides IKsControl support through synchronous calls to the driver containing the filter, using <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>.

The most common usage of <b>KsPinGetConnectedFilterInterface</b> is to acquire the control interface for the filter to which <i>Pin</i> attaches. This control interface can then be used for property, method, or event calls down to the connected pin, or can query for interfaces that have been aggregated onto the connected filter. (If the connected filter is an AVStream filter; AVStream provides thunking only for <a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a> and <b>IUnknown</b> for non-AVStream filters).

The thunk is created only if<i> Pin</i> is a source pin; thus, the calls only work if one or more of the following is true:

<ul>
<li>
The connection is intra-AVStream (<i>Pin</i>'s connected pin is an AVStream pin).

</li>
<li>
<i>Pin</i> is a source pin.

</li>
</ul>
Otherwise, STATUS_UNSUCCESSFUL is returned.




## -see-also

<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>



<a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetConnectedFilterInterface function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

