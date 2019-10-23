---
UID: NN:ks.IKsDeviceFunctions
title: IKsDeviceFunctions (ks.h)
description: The IKsDeviceFunctions interface is a COM-style interface implemented on AVStream devices. This interface is available in Windows Server 2003 SP1 and later versions of Windows.
old-location: stream\iksdevicefunctions.htm
tech.root: stream
ms.assetid: d29e7b39-5fcf-4543-9363-6f8ac6a9c7dc
ms.date: 04/23/2018
ms.keywords: IKsDeviceFunctions, IKsDeviceFunctions interface [Streaming Media Devices], IKsDeviceFunctions interface [Streaming Media Devices],described, avintfc_68e124c6-7a91-4c68-8327-e2c83b982699.xml, ks/IKsDeviceFunctions, stream.iksdevicefunctions
ms.topic: interface
f1_keywords:
 - "ks/IKsDeviceFunctions"
req.header: ks.h
req.include-header: 
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ks.h
api_name:
- IKsDeviceFunctions
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsDeviceFunctions interface


## -description


The IKsDeviceFunctions interface is a COM-style interface implemented on AVStream devices. This interface is available in Windows Server 2003 SP1 and later versions of Windows.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsDeviceFunctions</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsDeviceFunctions</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsDeviceFunctions</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-iksdevicefunctions-registeradapterobjectex">RegisterAdapterObjectEx</a>
</td>
<td align="left" width="63%">
Registers a DMA adapter object with AVStream. All drivers compiled for Win64 should use this method instead of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdeviceregisteradapterobject">KsDeviceRegisterAdapterObject</a>.

</td>
</tr>
</table> 

