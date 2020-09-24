---
UID: NF:ksproxy.IKsAggregateControl.KsAddAggregate
title: IKsAggregateControl::KsAddAggregate (ksproxy.h)
description: The KsAddAggregate method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the IKsAggregateControl interface.
old-location: stream\iksaggregatecontrol_ksaddaggregate.htm
tech.root: stream
ms.assetid: 9808bdb9-17f9-4a80-90c7-e85ab35b74ae
ms.date: 04/23/2018
keywords: ["IKsAggregateControl::KsAddAggregate"]
ms.keywords: IKsAggregateControl interface [Streaming Media Devices],KsAddAggregate method, IKsAggregateControl.KsAddAggregate, IKsAggregateControl::KsAddAggregate, KsAddAggregate, KsAddAggregate method [Streaming Media Devices], KsAddAggregate method [Streaming Media Devices],IKsAggregateControl interface, ksproxy/IKsAggregateControl::KsAddAggregate, ksproxy_1c56f07f-a830-4c2b-80ae-a18f14588bd3.xml, stream.iksaggregatecontrol_ksaddaggregate
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsAggregateControl::KsAddAggregate
 - ksproxy/IKsAggregateControl::KsAddAggregate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsAggregateControl.KsAddAggregate
---

# IKsAggregateControl::KsAddAggregate


## -description

The <b>KsAddAggregate</b> method adds a COM server as an aggregate provider to the list of interface providers for the KS object that exposes the <a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksaggregatecontrol">IKsAggregateControl</a> interface.

## -parameters

### -param AggregateClass 

[in]
Identifies the COM server to add.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksaggregatecontrol">IKsAggregateControl</a>



<a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksaggregatecontrol-ksremoveaggregate">IKsAggregateControl::KsRemoveAggregate</a>