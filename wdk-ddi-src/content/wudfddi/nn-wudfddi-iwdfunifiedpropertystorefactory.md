---
UID: NN:wudfddi.IWDFUnifiedPropertyStoreFactory
title: IWDFUnifiedPropertyStoreFactory
author: windows-driver-content
description: The IWDFUnifiedPropertyStoreFactory interface is a factory interface that is used to create a unified property store interface.
old-location: wdf\iwdfunifiedpropertystorefactory.htm
old-project: wdf
ms.assetid: 34884B88-187A-4079-843D-F777287442F7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfunifiedpropertystorefactory, IWDFUnifiedPropertyStoreFactory interface, IWDFUnifiedPropertyStoreFactory interface, described, IWDFUnifiedPropertyStoreFactory, wudfddi/IWDFUnifiedPropertyStoreFactory, umdf.iwdfunifiedpropertystorefactory
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFUnifiedPropertyStoreFactory
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFUnifiedPropertyStoreFactory interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFUnifiedPropertyStoreFactory</b> interface is a factory interface that is used to create a unified property store interface.


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
</table>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451406">RetrieveUnifiedDevicePropertyStore</a> method retrieves a unified property store interface.

 


## -remarks


A unified property store interface is exposed only from the device object. To retrieve this interface, the driver can call <b>IWDFDevice::QueryInterface</b> or <b>IWDFDeviceInitialize::QueryInterface</b>. If required, the driver can then access the properties before creating the device.

For related information, see <a href="https://msdn.microsoft.com/51105f84-38d8-4005-a3fd-4beccc0a2a39">Unified Device Property Model</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfunifiedpropertystore.md">IWDFUnifiedPropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUnifiedPropertyStoreFactory interface%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

