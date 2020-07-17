---
UID: NF:ks.KsPinGetConnectedFilterInterface
title: KsPinGetConnectedFilterInterface function (ks.h)
description: The KsPinGetConnectedFilterInterface function queries the filter to which Pin is connected in order to obtain a pointer to a COM interface.
old-location: stream\kspingetconnectedfilterinterface.htm
tech.root: stream
ms.assetid: 19fb7a3e-d795-4d5a-9f28-cfbf37dbcd96
ms.date: 04/23/2018
keywords: ["KsPinGetConnectedFilterInterface function"]
ms.keywords: KsPinGetConnectedFilterInterface, KsPinGetConnectedFilterInterface function [Streaming Media Devices], avfunc_d6f6f675-4d44-47c8-aa37-9ad533966603.xml, ks/KsPinGetConnectedFilterInterface, stream.kspingetconnectedfilterinterface
f1_keywords:
 - "ks/KsPinGetConnectedFilterInterface"
 - "KsPinGetConnectedFilterInterface"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetConnectedFilterInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetConnectedFilterInterface function


## -description


The<b> KsPinGetConnectedFilterInterface</b> function queries the filter to which <i>Pin</i> is connected in order to obtain a pointer to a COM interface.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure. The filter to which this pin is attached is queried for the requested interface.


### -param InterfaceId [in]

A pointer to a GUID representing the interface ID for the interface to obtain. A <b>QueryInterface</b> call is automatically performed for this interface.


### -param Interface [out]

A pointer to a PVOID. As in COM, the resulting interface pointer is deposited into <i>*Interface</i>. This interface has a corresponding reference count and <i>must</i> be released by the caller as in COM.


## -returns



<b>KsPinGetConnectedFilterInterface</b> returns STATUS_SUCCESS if the interface exists on the connected filter or in the AVStream thunk. If STATUS_SUCCESS is returned, the interface pointer is deposited into <i>*Interface</i>. Otherwise, it returns STATUS_NOINTERFACE. Note that this corresponds to the COM HRESULT E_NOINTERFACE.




## -remarks



By default, objects support the <b>IUnknown</b> interface and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a> interface. If the filter and connected pin are AVStream objects, the query and the returned interface pointer are direct calls to the other driver. However, if the connected pin and filter do not belong to an AVStream driver, a thunk is created that provides IKsControl support through synchronous calls to the driver containing the filter, using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>.

The most common usage of <b>KsPinGetConnectedFilterInterface</b> is to acquire the control interface for the filter to which <i>Pin</i> attaches. This control interface can then be used for property, method, or event calls down to the connected pin, or can query for interfaces that have been aggregated onto the connected filter. (If the connected filter is an AVStream filter; AVStream provides thunking only for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a> and <b>IUnknown</b> for non-AVStream filters).

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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nn-ks-iksreferenceclock">IKsReferenceClock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetreferenceclockinterface">KsPinGetReferenceClockInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
 

 

