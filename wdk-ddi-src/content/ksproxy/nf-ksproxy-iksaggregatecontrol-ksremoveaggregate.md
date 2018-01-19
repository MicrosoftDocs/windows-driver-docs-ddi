---
UID: NF:ksproxy.IKsAggregateControl.KsRemoveAggregate
title: IKsAggregateControl::KsRemoveAggregate method
author: windows-driver-content
description: The KsRemoveAggregate method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the IKsAggregateControl interface.
old-location: stream\iksaggregatecontrol_ksremoveaggregate.htm
old-project: stream
ms.assetid: f625b1ed-ccab-4072-9eb9-c4ebbddb1199
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsAggregateControl, IKsAggregateControl::KsRemoveAggregate, KsRemoveAggregate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsAggregateControl.KsRemoveAggregate
req.alt-loc: ksproxy.h
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
req.typenames: PIPE_STATE
---

# IKsAggregateControl::KsRemoveAggregate method



## -description
The <b>KsRemoveAggregate</b> method removes a previously added COM server aggregate provider from the list of interface providers for the KS object that exposes the <a href="..\ksproxy\nn-ksproxy-iksaggregatecontrol.md">IKsAggregateControl</a> interface.



## -syntax

````
HRESULT KsRemoveAggregate(
  [in] REFGUID AggregateClass
);
````


## -parameters

### -param AggregateClass [in]

Identifies the COM server to remove.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559713">IKsAggregateControl::KsAddAggregate</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksaggregatecontrol.md">IKsAggregateControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAggregateControl::KsRemoveAggregate method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

