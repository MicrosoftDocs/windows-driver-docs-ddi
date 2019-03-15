---
UID: NN:wudfddi.IWDFUnifiedPropertyStoreFactory
title: IWDFUnifiedPropertyStoreFactory (wudfddi.h)
description: The IWDFUnifiedPropertyStoreFactory interface is a factory interface that is used to create a unified property store interface.
old-location: wdf\iwdfunifiedpropertystorefactory.htm
tech.root: wdf
ms.assetid: 34884B88-187A-4079-843D-F777287442F7
ms.date: 02/26/2018
ms.keywords: IWDFUnifiedPropertyStoreFactory, IWDFUnifiedPropertyStoreFactory interface, IWDFUnifiedPropertyStoreFactory interface,described, umdf.iwdfunifiedpropertystorefactory, wdf.iwdfunifiedpropertystorefactory, wudfddi/IWDFUnifiedPropertyStoreFactory
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUnifiedPropertyStoreFactory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUnifiedPropertyStoreFactory interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUnifiedPropertyStoreFactory</b> interface is a factory interface that is used to create a unified property store interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUnifiedPropertyStoreFactory</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IWDFUnifiedPropertyStoreFactory</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUnifiedPropertyStoreFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451406">RetrieveUnifiedDevicePropertyStore</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451406">RetrieveUnifiedDevicePropertyStore</a> method retrieves a unified property store interface.

</td>
</tr>
</table> 


## -remarks



A unified property store interface is exposed only from the device object. To retrieve this interface, the driver can call <b>IWDFDevice::QueryInterface</b> or <b>IWDFDeviceInitialize::QueryInterface</b>. If required, the driver can then access the properties before creating the device.

For related information, see <a href="https://msdn.microsoft.com/51105f84-38d8-4005-a3fd-4beccc0a2a39">Unified Device Property Model</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451399">IWDFUnifiedPropertyStore</a>
 

 

